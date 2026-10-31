---
id: network-access-and-data-privacy
url: merger/net/network-access-and-data-privacy
title: Network access and data privacy
weight: 10
description: "Learn when GroupDocs.Merger for .NET accesses the network, what never leaves your machine, and how to run it offline or in an air-gapped environment."
keywords: network access, data privacy, offline, air-gapped, SSRF, external resources, metered license, GroupDocs.Merger
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: True
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** is an on-premise library: it runs inside your own process, on your own infrastructure. GroupDocs never receives the documents you process.

By default, processing a document does not request the resources it references. The library's own code contacts a server only in the situations listed below, and each of them is either off by default or something your code asks for explicitly.

## What never leaves your machine

* The content of the documents you process and of the files they produce.
* File names and paths.
* Usage data. The library's code reports usage only when you use a [metered license](#metered-licensing), and then only quantities, never document content.

## When GroupDocs.Merger accesses the network

### Loading external resources referenced by a document

**Off by default.** A document can reference content it does not carry: a remote image or stylesheet in an HTML page, a linked picture in a Word document or a presentation. GroupDocs.Merger does not load such resources unless you allow them: every `LoadOptions` constructor sets `SkipExternalResources` to `true`, and a `Merger` created without load options uses the same default.

You can allow specific resources by absolute URI prefix with `WhitelistedResources`, all of them with `SkipExternalResources = false`, or decide for each resource in your own code with `ExternalResourceHandler`, which can also supply a resource's content so that no request is made. See [Skip loading of external resources]({{< ref "merger/net/developer-guide/loading/skip-external-resources.md" >}}) for the rules, the supported formats and examples.

### Metered licensing

**Opt-in.** With a metered license (`Metered.SetMeteredKey`), the library reports usage quantities — the amount of data processed and the credits consumed — together with your subscription identifiers to the GroupDocs billing service. The report carries no document content, file names or paths. Metered licensing needs network access, so it does not suit air-gapped systems: use a license file or a license stream there instead.

Setting a license from a file or from a stream with `License.SetLicense` never accesses the network. See [Licensing]({{< ref "merger/net/getting-started/licensing-and-subscription.md" >}}).

### Code you supply

GroupDocs.Merger itself makes no request when you load a document from a URL. The library has no URL-based constructor: the [load from URL]({{< ref "merger/net/developer-guide/loading/loading-documents-from-different-sources/load-document-from-url.md" >}}) example downloads the file in your code and passes the stream to `Merger`.

## How this is verified

The product's test suite processes probe documents whose external references point at a local test listener — HTML, MHTML, word processing documents, presentations, spreadsheets, SVG, EPUB, PDF, Visio, OneNote, plain text, ZIP and TAR archives and more — with every operation that applies to them, and fails if any operation under default options sends a request to it. It also checks that references a document only mentions, such as hyperlinks and form actions, are never requested even when external resources are allowed, and that every `LoadOptions` constructor denies external resources. The suite runs on .NET Framework 4.6.2, .NET 6.0 and .NET 10.0, on Windows and Linux.

The measurement has limits: it observes requests to the references planted in the probe documents, and formats without a probe document, such as XPS, PostScript and TeX, are not measured.

These statements apply to version 26.10 and later.

## Running offline

To run GroupDocs.Merger without any network access:

1. Keep the default `SkipExternalResources = true`, or allow only `file:` prefixes in `WhitelistedResources`.
2. Set the license from a local file or a stream.
3. Do not use a metered license.
4. Make sure your own loading code does not access the network.

To enforce this independently of the library, block outbound traffic for the process at the network or container level.

## Diagnosing an unexpected request

If you observe an outbound request from a process that uses GroupDocs.Merger:

1. Capture the traffic and note the requested URL.
2. Search the documents being processed for that URL. If a document references it, check the load options of that `Merger`: `SkipExternalResources` set to `false`, a `WhitelistedResources` entry that matches it, or an `ExternalResourceHandler` that allows it.
3. Check whether the request goes to the GroupDocs billing service: a metered license.
4. Check your own loading code.
5. Block egress for the process and repeat the operation to confirm the source.

If the request comes from GroupDocs.Merger itself under default options, please report it on the [free support forum](https://forum.groupdocs.com/c/merger).

## More resources

* [Skip loading of external resources]({{< ref "merger/net/developer-guide/loading/skip-external-resources.md" >}})
* [Licensing]({{< ref "merger/net/getting-started/licensing-and-subscription.md" >}})
* [System requirements]({{< ref "merger/net/getting-started/system-requirements.md" >}})
* [GroupDocs security and customer data](https://about.groupdocs.com/security/customer-data-and-security/)
