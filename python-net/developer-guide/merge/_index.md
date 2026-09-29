---
id: merge
url: merger/python-net/merge
title: Merge files
weight: 3
description: "This article explains how to merge files of PDF, Microsoft Word, Excel and PowerPoint and other formats using GroupDocs.Merger for Python via .NET API."
keywords: Merge files, Combine files, Merge documents, Merge document with GroupDocs.Merger for Python via .NET
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
structuredData:
    showOrganization: True
---

GroupDocs.Merger for Python via .NET lets you combine multiple documents of the same family into a single output file with just a few lines of Python code. All content — text, images, tables, graphs, forms, and embedded objects — is faithfully preserved in the result.

The library handles the complexities of each file format internally, so you do not need to understand proprietary format internals or rely on any third-party desktop software. The API is identical regardless of format: load the base document with `Merger`, call `join` once for every additional file, then call `save`.

{{< alert style="info" >}}
**Try online**

You can try merging files online and download the results for free using GroupDocs.Merger [Live Demo](https://products.groupdocs.app/merger).
{{< /alert >}}

## Steps to merge documents

1. Install the package: `pip install groupdocs-merger-net`.
2. Import `Merger` from `groupdocs.merger`.
3. Open the first (base) document with `Merger("./input.<ext>")` inside a `with` block.
4. Call `merger.join("./input2.<ext>")` for each additional document to append.
5. Call `merger.save("./output.<ext>")` to write the combined result.

## Supported formats

See the full list in [Supported Document Formats]({{< ref "merger/python-net/getting-started/supported-document-formats.md" >}}).

## Per-format guides

Choose the guide for the format you want to merge:

- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [Merge Word documents]({{< ref "merger/python-net/developer-guide/merge/word.md" >}})
- [Merge Excel spreadsheets]({{< ref "merger/python-net/developer-guide/merge/excel.md" >}})
- [Merge PowerPoint presentations]({{< ref "merger/python-net/developer-guide/merge/powerpoint.md" >}})
- [Merge images]({{< ref "merger/python-net/developer-guide/merge/images.md" >}})
- [Merge text files]({{< ref "merger/python-net/developer-guide/merge/text.md" >}})
- [Merge EPUB files]({{< ref "merger/python-net/developer-guide/merge/epub.md" >}})
- [Merge HTML files]({{< ref "merger/python-net/developer-guide/merge/html.md" >}})
- [Merge archives]({{< ref "merger/python-net/developer-guide/merge/archives.md" >}})

## See also

- [Split a document]({{< ref "merger/python-net/developer-guide/single-document-operations/split-document.md" >}})
- [Get document information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}})
