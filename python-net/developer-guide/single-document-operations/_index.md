---
id: single-document-operations
url: merger/python-net/single-document-operations
title: Single document operations
linkTitle: Single document operations
weight: 4
description: "Learn how to move document pages, remove document pages, split document into separate pages, swap document pages positions, extract specific pages from document, change page orientation and rotate pages using GroupDocs.Merger for Python via .NET."
keywords: Move document page, remove document page, extract document page, swap document pages, change page orientation, rotate pages, split document, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you rearrange, filter, and transform individual pages within a single document — without merging multiple files. Use the operations below to build page-level document processing pipelines entirely in Python.

## Available operations

| Operation | Description |
| --- | --- |
| [Move page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page" >}}) | Relocate any page to a different position in the page order. |
| [Remove pages]({{< ref "merger/python-net/developer-guide/single-document-operations/remove-pages" >}}) | Delete one or more pages from a document. |
| [Split document]({{< ref "merger/python-net/developer-guide/single-document-operations/split-document" >}}) | Split a document into separate files by page numbers or page intervals. |
| [Split text file]({{< ref "merger/python-net/developer-guide/single-document-operations/split-text-file" >}}) | Split a plain-text file into multiple files by line numbers. |
| [Extract pages]({{< ref "merger/python-net/developer-guide/single-document-operations/extract-pages" >}}) | Create a new document that contains only selected pages from the source. |
| [Swap pages]({{< ref "merger/python-net/developer-guide/single-document-operations/swap-pages" >}}) | Exchange the positions of two pages within a document. |
| [Change page orientation]({{< ref "merger/python-net/developer-guide/single-document-operations/change-page-orientation" >}}) | Switch pages between Portrait and Landscape orientation. |
| [Rotate pages]({{< ref "merger/python-net/developer-guide/single-document-operations/rotate-pages" >}}) | Rotate pages by 90, 180, or 270 degrees. |

## Quick-start example

The snippet below loads a PDF, removes page 2, and saves the result — illustrating the common pattern shared by all single-document operations.

```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import RemoveOptions

def quick_remove_page():
    # Load the source document
    with Merger("./input.pdf") as merger:
        # Remove page 2
        merger.remove_pages(RemoveOptions([2]))
        # Save the modified document
        merger.save("./output.pdf")

if __name__ == "__main__":
    quick_remove_page()
```

{{< alert style="tip" >}}
All single-document operations follow the same three-step pattern: **load** with `Merger`, **call the operation method**, then **save** with `merger.save()`.
{{< /alert >}}

## API reference

- [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main entry-point class.
- [groupdocs.merger.domain.options](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/) — all option and enum types.
