---
id: how-to-create-pdf-binder-using-csharp
url: merger/net/getting-started/use-cases/how-to-create-pdf-binder-using-csharp
title: "PDF Binder Demo: Merging Multiple Formats into a Single PDF"
weight: 500
description: "An engineering walkthrough of four ways to wire GroupDocs.Merger for .NET into a real document pipeline — from a single-shot controller to a full microservice split."
keywords: "GroupDocs.Merger, PDF merging, .NET, document consolidation, cross-format conversion, binder, DOCX, XLSX, PDF"
productName: "GroupDocs.Merger for .NET"
structuredData:
  showOrganization: true
toc: true
hideChildren: false
draft: false
---

![PDF binder produced from DOCX, XLSX, and PDF sources — captured from a live run](/merger/net/images/how-to-create-pdf-binder-using-csharp/result.gif)

## Why this page exists

This page is for the engineer who already believes the merge works and now has to decide where it lives in the system. Controller action? Background worker? Its own service behind a queue? The library looks the same in every case — the wiring around it is what decides whether the pipeline is cheap to run at three requests per hour or three hundred per minute.

We'll walk through four deployment shapes in order of rising complexity, show the exact code that stays the same across all of them, and point out where each one starts to hurt.

## Audience and assumptions

Written for senior .NET developers and architects who need to embed merging into a larger workflow. We assume you're comfortable with async patterns, container orchestration, and the basic GroupDocs.Merger API surface. If you want an introduction to the API first, read the blog walkthrough — this page picks up where that one leaves off.

**What you'll need to follow along:**
- .NET 6.0 SDK on your build agents.
- GroupDocs.Merger NuGet package (v23.9 or later).
- A target runtime you've already profiled — these decisions depend on CPU and I/O characteristics.

## Four shapes at a glance

| Shape | Complexity | Throughput | Latency | How it scales | Resource profile |
|-------|------------|------------|---------|----------------|------------------|
| **In-process synchronous** | Low | Medium | Low | Vertical only | CPU-hungry during convert |
| **Drop-folder batch worker** | Medium | High | Medium (seconds) | Horizontal by folder | Steady, disk-bound |
| **Async extract/slice service** | High | Very High | Low (async) | Horizontal, queue-fed | Light, memory-only |
| **Metadata microservice** | High | High | Medium | Horizontal, cache-friendly | Minimal |

Each of these uses the same `Merger` API — the differences are all in how you hand files to it and what you do with the output.

## Shape 1 — In-process synchronous merge

### When this is the right call

A controller receives a small set of uploaded files, the user is watching a spinner, and you need a response within a second or two. The caller supplies the file list and the order, so there's nothing to decide at runtime.

**Pattern:** Facade around the SDK, invoked directly from the controller.
**Concurrency:** Single-threaded per request; thread pool handles the fan-out across requests.
**State:** Per-request; nothing persists beyond the HTTP response.

### Wiring

```csharp
Console.WriteLine($"Primary source: {sourcePaths[0]}");
using var merger = new Merger(sourcePaths[0]);

var joinOptions = new JoinOptions();
for (int i = 1; i < sourcePaths.Length; i++)
{
    Console.WriteLine($"Joining: {sourcePaths[i]}");
    merger.Join(sourcePaths[i], joinOptions);
}

merger.Save(outputPath);
Console.WriteLine(
    $"Unified PDF binder saved to: {Path.GetFullPath(outputPath)}");
return outputPath;
```

Why this stays boring: `Merger` owns the file handles until `Dispose()`, `Join` appends each source, and the output format is decided by whichever file you opened first. Hand the SDK a PDF as `sourcePaths[0]` and the DOCX/XLSX on the tail end get converted in-flight — no temp files on your disk, no second library.

### What it costs you

A 15-page DOCX plus a five-sheet XLSX plus a two-page PDF typically lands in the 300–700 ms range on modest hardware. Memory peaks while conversion runs; large spreadsheets are usually the culprit when a pod OOMs.

### Scaling notes

- **Horizontal:** Standard stateless scale-out behind a load balancer. Nothing special here.
- **Vertical:** Each request is CPU-bound through the convert path, so a faster box helps.
- **What will bite you:** A single rogue 400-page workbook will pin one core for seconds and tie up a worker thread. Set sensible upload size limits upstream.

### Operational notes

- Log start time, finish time, source count, and final page count as one line per request — makes triage a grep instead of a debugger session.
- Wrap in a short retry on transient I/O; the SDK's own errors are rarely transient, so don't retry those.
- Expose `merge_duration_ms` as a histogram so p99 isn't a surprise.

## Shape 2 — Drop-folder batch worker

### When this is the right call

Something upstream — an SFTP landing zone, an inbound-email processor, a nightly finance export — dumps mixed-format files into a directory. You need to turn each folder into a binder on a schedule, not per-request.

**Pattern:** Producer-consumer. Upstream drops files; worker claims a folder, produces a binder, moves the folder to "done."
**Concurrency:** Parallel over folders; sequential within a folder (one `Merger` per binder).
**State:** None persists between runs; the filesystem is the queue.

### Wiring

```csharp
// Pull only the extensions the worker knows how to handle, and push
// any PDF to the front so Merger uses it as the primary document.
// Using ThenBy(f) keeps runs deterministic across machines.
var extensions = new[] { ".pdf", ".docx", ".xlsx" };
var files = Directory
    .EnumerateFiles(folderPath)
    .Where(f => extensions.Contains(
        Path.GetExtension(f).ToLowerInvariant()))
    .OrderBy(f => Path.GetExtension(f).ToLowerInvariant() == ".pdf"
        ? 0 : 1)
    .ThenBy(f => f)
    .ToArray();

if (files.Length == 0)
{
    throw new InvalidOperationException(
        $"No supported documents found in '{folderPath}'.");
}

Console.WriteLine(
    $"Folder binder: discovered {files.Length} files in {folderPath}");
return MergeMultipleFormatsIntoPdf(files, outputPath);
```

The ordering step is worth staring at. GroupDocs.Merger inherits the output format from the first file handed to `new Merger(...)`. A folder that happens to sort DOCX before PDF would produce a DOCX binder — correct, but not what downstream expected. Promoting the PDF to index 0 makes the output format a property of the ingested mix, not of filename luck.

### What it costs you

Folder of 200 documents, roughly 800 pages total: around 2 seconds once the files are on local SSD. Network-mounted source folders roughly double that and hold you I/O-bound, not CPU-bound.

### Scaling notes

- **Horizontal:** Shard by folder — one worker per tenant, per region, or per hash-bucket of folder names. Coordinate with a queue if shared state matters.
- **Vertical:** More RAM helps large spreadsheets; more CPU helps DOCX-heavy mixes. Disks matter more than either.
- **What will bite you:** A partner who ships 50 MB of embedded images in a single XLSX. Consider an upstream pre-flight that flags suspicious sizes before the worker wakes up.

### Operational notes

- Emit `files_processed` and `bytes_merged` per run; they're the two numbers that predict SLA breaches.
- Quarantine failed folders to a `failed/` sibling and keep going — one bad file shouldn't stop the batch.
- If a folder is retried, version the output filename (`binder-YYYYMMDD-HHmmss.pdf`) so nothing is silently overwritten.

## Shape 3 — Asynchronous page-extract service

### When this is the right call

Your binders already exist in storage, and the next consumer only wants a slice — a cover page, an appendix, a specific page range. Re-merging sources for this is wasteful; reading the finished PDF and extracting pages is seconds faster.

**Pattern:** Command/query split. Merge is the command (elsewhere). This service only answers the query "hand me pages [1, 3, 7] of binder X."
**Concurrency:** Async I/O; the SDK calls run on pool threads behind `Task.Run`.
**State:** None in the service; result blobs land in object storage.

### Wiring

```csharp
using var merger = new Merger(binderPath);
merger.ExtractPages(new ExtractOptions(pages));
merger.Save(outputPath);

Console.WriteLine(
    $"Extracted pages [{string.Join(",", pages)}] to "
    + Path.GetFullPath(outputPath));
return outputPath;
```

No conversion happens here — the input is already a PDF and the output is a PDF — so the latency is dominated by the read of the source blob. That makes it a natural fit for a queue-fed worker: one request in, one blob out, nothing to contend with.

### What it costs you

Well under a second for typical binders. Very large PDFs (500 MB+) lift memory noticeably during extraction; treat that as the scaling cliff.

### Scaling notes

- **Horizontal:** Stateless workers behind a queue. Throughput scales almost linearly with worker count until your storage starts to push back.
- **Vertical:** Rarely needed. Extract is cheap.
- **What will bite you:** Requesting non-existent pages. Validate `pages` against `GetDocumentInfo().PageCount` before calling `ExtractPages` — otherwise the SDK throws and you've burned a blob read.

### Operational notes

- Track extract latency separately from merge latency; they're on different performance curves.
- Cache extracts by (binder-hash, page-set) if the same slices are requested repeatedly. Small cache, huge throughput win.
- Return a deterministic output URL so retries are idempotent.

## Shape 4 — Metadata microservice

### When this is the right call

Downstream services ask "how many pages does this binder have?" dozens of times per binder — for routing, for pagination, for building a dynamic TOC. Each of those questions is cheap, but they stack up if every caller reopens the PDF.

**Pattern:** Query-only service. No writes, no merges, just metadata reads that fit behind a cache.
**Concurrency:** Synchronous request-response. Fast enough that async doesn't buy anything.
**State:** A read-through cache (Redis) in front of the SDK call.

### Wiring

```csharp
using var merger = new Merger(pdfPath);
var info = merger.GetDocumentInfo();
return info.PageCount;
```

On a cold miss this is milliseconds because the SDK reads the PDF trailer rather than parsing pages. On a cache hit it's sub-millisecond.

### Scaling notes

- **Horizontal:** Tiny pods, big replica counts. One CPU core per pod is usually plenty.
- **Vertical:** Don't bother.
- **What will bite you:** Cache staleness if a binder is ever mutated in place. Prefer immutable output names so a new binder forces a new cache key.

### Operational notes

- Expose `pageCount` as a gauge metric tagged by document type — useful trend data for capacity planning.
- Return 404 (not 500) for a binder that doesn't exist; downstream orchestrators should be able to distinguish "not here" from "broken."
- If you front this with Redis, give the TTL a ceiling so a replaced binder eventually self-corrects even if invalidation was missed.

## Numbers from one reference environment

Your mileage will differ, but these are the ballpark numbers from the environment we benchmarked.

**Environment:** Windows Server 2022, .NET 6 LTS, 8-core Intel Xeon, 16 GB RAM, NVMe SSD, GroupDocs.Merger v23.9.

| Shape | Throughput | Latency (typical) | Memory | Best fit |
|-------|------------|-------------------|--------|----------|
| **In-process synchronous** | Medium | ~300 ms | Holds all source streams | Interactive APIs |
| **Drop-folder batch worker** | High | ~2 s per 200-file folder | One file in flight at a time | Scheduled back-office jobs |
| **Async extract service** | Very High | ~150 ms | Minimal | Slice-on-demand delivery |
| **Metadata microservice** | Very High | ~20 ms | Negligible | High-QPS page-count queries |

Read that as a shape comparison, not a benchmark promise. The interactive API is faster per request; the batch worker is faster per document because the SDK init amortizes across the folder.

## Patterns worth naming

### Facade over the SDK

A thin service interface (`IDocumentBinder`) in front of `Merger` makes it easy to swap implementations for tests, and it keeps your controllers clean.

**When:** Any shape with more than one caller.
**Trade-off:** One more file in the solution. Worth it.

### Producer-consumer queue

Decouple ingestion from merging via a queue. The ingestion side doesn't care how fast the worker runs; the worker doesn't care where files came from.

**When:** Drop-folder shape at any meaningful volume.
**Trade-off:** Queue as operational surface — dead-letter policy, poison-message handling, etc.

### CQRS split for merge vs. extract

Keep the "build the binder" and "slice the binder" paths in separate services. They have very different performance profiles and scaling curves, and jamming them into one process makes capacity planning harder than it needs to be.

**When:** Once you have a real page-extract workload.
**Trade-off:** Two services to deploy. Worth it when the read path has 10× the QPS of the write path.

## Embedding into an existing stack

### Microservices

Package each shape as its own container. Use gRPC if your ecosystem is internal; stick with REST if you have external consumers. Add a sidecar for logs and health checks — nothing bespoke.

### Inside a monolith

All of the shapes compile into the same assembly if that's your constraint. Wire them in via DI and keep the `Merger` interactions behind that facade so you can pull them out later without a rewrite.

### Hybrid

Merging on-prem (because the documents can't leave the building), metadata in the cloud (because it's the hot-read path). This is the most common shape we see at regulated customers.

## Security and compliance

### Security

- Put temporary files under a directory that's ACL-locked to the worker identity. Delete eagerly; don't rely on the OS temp cleanup.
- Validate every incoming path against a root before opening it. Path-traversal is a real risk when the filename is user-influenced.
- TLS on every endpoint, and mTLS between services if the environment supports it.

### Compliance

- For archival, ask the SDK for PDF/A-1b output via `SaveOptions`. Don't assume the input PDFs were compliant just because they opened.
- Keep an audit record of `(requestId, sources, output, pageCount, timestamp)` for every merge. That's the record regulators want when they ask "what was in this binder."

## Monitoring and observability

### Metrics that earn their keep

- `merge_duration_ms` (histogram)
- `batch_files_processed` (counter)
- `extract_latency_ms` (histogram)
- `metadata_query_rate` (counter)

### Logging

Structured JSON, one line per operation, including request ID, operation type, file count, input byte total, output byte total, page count, and outcome. That's the schema that lets you build reliable dashboards.

### Alerts

Page on sustained `merge_duration_ms` above threshold (not spikes — spikes are usually large documents). Page on error rate above 1% sustained for five minutes.

## Troubleshooting

### Common slow paths

- **Large embedded images in XLSX.** The convert path re-rasterizes; a pre-merge compression step helps.
- **Shared network storage.** Copy sources to local scratch before merging; the round-trip latency adds up fast.

### Easy wins

- Reuse `Merger` across batch operations where possible — init isn't free.
- Turn on `SaveOptions.Compress` for output PDFs; the size reduction is usually meaningful.

## Decisions worth writing down

### ADR 1 — Sync vs. async

Sync for interactive APIs (latency matters, volume is low). Async/queue-fed for batch and extract (latency is fine, volume is high). Don't mix the two in one service.

### ADR 2 — Scale out, not up

We picked horizontal scaling behind orchestration over vertical scaling on big boxes. Cheaper per unit of throughput, and no single-node failure can stall the pipeline.

## Wrap-up

Four shapes, one SDK. The synchronous shape is the right default for a small interactive feature. The batch worker is the right default once volume shows up. The extract service is the quiet win — it turns a "please send me just the cover page" email into an automated endpoint. The metadata service is almost free and pays for itself the first time a downstream asks for page counts at scale.

Pick the shape, keep `Merger` behind a facade, log the page count after every write, and you'll have a pipeline that's cheap to run and loud when it breaks.

**Before production:**
- Read the source of the sample project end-to-end.
- Benchmark with your real document mix, not synthetic ones.
- Turn on the monitoring and alerting described above before the first real request.
- Swap the evaluation key for a real license so the output stops carrying watermarks.

**Additional resources:**
- [API Reference](https://reference.groupdocs.com/merger/net/) — full API surface for GroupDocs.Merger for .NET
- [Product documentation](https://docs.groupdocs.com/merger/net/) — getting started and advanced topics
- [GitHub repository](https://github.com/groupdocs-merger/GroupDocs.Merger-for-.NET) — complete source code and more examples
