---
id: features-overview
url: merger/python-net/getting-started/features-overview
title: Features Overview
linkTitle: Features Overview
weight: 1
description: "Key features of GroupDocs.Merger for Python via .NET — merge, split, page operations, rotation, password security, document inspection, page preview, and AI-pipeline integration."
keywords: features, merge, split, extract pages, remove pages, rotate pages, password, preview, document info, python, GroupDocs.Merger
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
aliases:
    - /merger/python-net/features-overview/
---

## Overview

GroupDocs.Merger for Python via .NET provides a comprehensive set of document manipulation features across **70+ supported formats** — Microsoft Office, PDF, OpenDocument, images, Visio diagrams, eBooks, archives, and more. It runs entirely on-premise, requires no third-party office applications, and ships as a pre-built wheel on Windows, Linux, and macOS.

See the full list of [supported formats]({{< ref "merger/python-net/getting-started/supported-document-formats.md" >}}) or browse the [Developer Guide]({{< ref "merger/python-net/developer-guide" >}}) for runnable examples of every API surface.

## Merge / Join

The core capability is combining multiple documents into one. You can merge entire documents or select specific pages or page ranges from each source document. Format-specific join options let you control how the documents are stitched together — for example, continuous section breaks for Word documents or bookmark preservation for PDFs.

- Merge whole documents — see [Merge Files]({{< ref "merger/python-net/developer-guide/merge" >}}).
- Merge specific pages from each source — see [Merge PDF]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}}) or any per-format merge page.
- Word-specific options (`WordJoinOptions`) and PDF-specific options (`PdfJoinOptions`) are documented per format in [Merge Files]({{< ref "merger/python-net/developer-guide/merge" >}}).

## Split

Split a document into a collection of smaller documents. You can emit one file per listed page, split by interval (every N pages), or split a plain-text file by line numbers.

- Split by page list or interval — see [Split Document]({{< ref "merger/python-net/developer-guide/single-document-operations/split-document.md" >}}).
- Split a text file at specific line numbers — see [Split Text File]({{< ref "merger/python-net/developer-guide/single-document-operations/split-text-file.md" >}}).

## Page Operations

GroupDocs.Merger exposes granular, page-level control over any document without requiring a round-trip through an office application.

### Extract Pages

Produce a new document that contains only the specified pages or page range from a source document. See [Extract Pages]({{< ref "merger/python-net/developer-guide/single-document-operations/extract-pages.md" >}}).

### Remove Pages

Remove one or more pages from a document by page number. See [Remove Pages]({{< ref "merger/python-net/developer-guide/single-document-operations/remove-pages.md" >}}).

### Swap Pages

Exchange the positions of two pages within a document. See [Swap Pages]({{< ref "merger/python-net/developer-guide/single-document-operations/swap-pages.md" >}}).

### Move Page

Move a single page to a different position within the page order. See [Move Page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page.md" >}}).

### Rotate Pages

Rotate selected pages by 90°, 180°, or 270° using `RotateMode` enum values. See [Rotate Pages]({{< ref "merger/python-net/developer-guide/single-document-operations/rotate-pages.md" >}}).

### Change Page Orientation

Switch selected pages between portrait and landscape orientation using `OrientationMode`. See [Change Page Orientation]({{< ref "merger/python-net/developer-guide/single-document-operations/change-page-orientation.md" >}}).

## Security

GroupDocs.Merger manages document password protection without requiring the document to be opened in an editor:

- **Add a password** — protect a document with a new password.
- **Update a password** — change an existing password after loading with the current one.
- **Remove a password** — strip protection after loading with the correct password.
- **Check protection** — call `merger.is_password_set()` to test whether a document is protected.

See [Security Operations]({{< ref "merger/python-net/developer-guide/security-operations" >}}) for runnable examples of each operation.

## Document Inspection

Read metadata from a document without modifying it — file type, page count, page dimensions, visibility flags, and file size. Enumerate all formats supported at runtime via `FileType.get_supported_file_types()`.

- Read document metadata — see [Get Document Information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}}).
- List all supported formats at runtime — see [Get Supported File Types]({{< ref "merger/python-net/developer-guide/get-supported-file-types.md" >}}).

## Page Preview

Generate raster image previews (PNG, JPEG, or BMP) of individual document pages. Previews are useful for displaying document thumbnails in a UI, validating page content before merging, or feeding page images into a vision model.

See [Page Preview]({{< ref "merger/python-net/developer-guide/page-preview.md" >}}) for a runnable example using the file-stream callback pattern.

## Loading Documents

GroupDocs.Merger accepts documents from local disk, binary streams (file handles, in-memory buffers), and password-protected files via `LoadOptions`.

- Load from local disk — see [Load from Local Disk]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-local-disk.md" >}}).
- Load from a stream — see [Load from Stream]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-stream.md" >}}).
- Load a password-protected file — see [Load Password Protected Document]({{< ref "merger/python-net/developer-guide/loading-documents/load-password-protected.md" >}}).

## AI / LLM Integration

GroupDocs.Merger is designed to be a first-class building block for AI document pipelines. The `groupdocs-merger-net` pip package ships an `AGENTS.md` file inside the wheel so AI coding assistants can discover the API surface automatically, and GroupDocs runs a public [MCP server](https://docs.groupdocs.com/mcp) for on-demand documentation lookups.

See [Agents and LLM Integration]({{< ref "merger/python-net/agents-and-llm-integration" >}}) for the full story — including a runnable pipeline that merges PDFs and extracts a page subset for downstream AI processing.

## On-Premise Deployment

No cloud calls, no outbound network traffic, no Microsoft Office or Adobe Acrobat installation required. The wheel is self-contained on Windows and ships its own native runtime libraries on Linux and macOS. See [System Requirements]({{< ref "merger/python-net/getting-started/system-requirements.md" >}}) for the short list of optional native packages (`libgdiplus`, `libfontconfig1`).
