---
id: loading-documents
url: merger/python-net/developer-guide/loading-documents
title: Loading Documents
linkTitle: Loading Documents
weight: 9
description: "Load documents into GroupDocs.Merger for Python via .NET from a local file path, a Python stream, or a password-protected file using the Merger class constructors and LoadOptions."
keywords: load document, load from local disk, load from stream, password-protected document, LoadOptions, Merger constructor, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) provides flexible ways to load a source document. The `Merger` class accepts a file path, a binary stream, or either combined with `LoadOptions` for password-protected and custom-loading scenarios.

## Merger Class Constructors

The following constructors are available for loading from a **file path**:

- **`Merger(file_path)`** — load a document from a local or relative file path.
- **`Merger(file_path, load_options)`** — load a document and supply additional load options (e.g. a password).
- **`Merger(file_path, load_options, settings)`** — load a document with load options and custom `MergerSettings`.

To load a document from a **stream**, pass any readable binary stream object:

- **`Merger(stream)`** — load from a binary file-like object.
- **`Merger(stream, load_options)`** — load from a stream with additional load options.
- **`Merger(stream, load_options, settings)`** — load from a stream with load options and custom settings.

All constructors support the Python context manager protocol (`with Merger(...) as merger:`), which automatically releases all managed resources when the block exits.

## Loading Guides

- [Load from local disk]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-local-disk.md" >}}) — open a document stored on the filesystem by passing a file path to the `Merger` constructor.
- [Load from stream]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-stream.md" >}}) — pass any binary readable stream (e.g. an open file handle) directly to `Merger`.
- [Load password-protected document]({{< ref "merger/python-net/developer-guide/loading-documents/load-password-protected.md" >}}) — supply the document password via `LoadOptions` to open encrypted files.

## See also

- [Security operations]({{< ref "merger/python-net/developer-guide/security-operations/_index.md" >}})
- [Get document information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}})
