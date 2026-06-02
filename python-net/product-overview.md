---
id: product-overview
url: merger/python-net/product-overview
title: GroupDocs.Merger for Python via .NET Overview
linkTitle: Product overview
weight: 1
description: "GroupDocs.Merger for Python via .NET merges, splits, and reorganises documents — PDF, DOCX, XLSX, PPTX, images, and more — entirely on-premise without Microsoft Office."
keywords: merger, merge, split, PDF, DOCX, XLSX, PPTX, images, eBook, page operations, password, preview, python, on-premise
productName: GroupDocs.Merger for Python via .NET
toc: True
---

## What is GroupDocs.Merger?

GroupDocs.Merger for Python via .NET is a native Python library that merges, splits, and reorganises documents across **70+ supported formats** — DOCX, PDF, XLSX, PPTX, images, Visio diagrams, eBooks, archives, and more. It runs entirely on-premise, requires no Microsoft Office or Adobe Acrobat installation, and ships as a pre-built wheel on Windows, Linux, and macOS.

Typical uses include:

- **Multi-document consolidation** — assemble a single report or package from multiple source files in one API call.
- **Selective page merges** — pull specific pages or page ranges from several documents and combine them into a new document.
- **Document assembly automation** — build dynamic documents programmatically as part of batch or pipeline workflows.
- **Access control** — protect sensitive documents with passwords and manage password changes or removal.
- **Page-level preparation** — reorder, rotate, extract, or remove individual pages before a document reaches its final destination.

## Key Capabilities

| Capability | Description |
|---|---|
| **Merge / Join** | Combine two or more documents — or selected pages from them — into a single output file. See [Merge Files]({{< ref "merger/python-net/developer-guide/merge" >}}). |
| **Split** | Divide a document into individual pages or multi-page segments by page list or interval. See [Split Document]({{< ref "merger/python-net/developer-guide/single-document-operations/split-document.md" >}}). |
| **Page Operations** | Extract, remove, swap, or move pages within a document. See [Single Document Operations]({{< ref "merger/python-net/developer-guide/single-document-operations" >}}). |
| **Rotation / Orientation** | Rotate pages 90°, 180°, or 270° and change page orientation between portrait and landscape. See [Rotate Pages]({{< ref "merger/python-net/developer-guide/single-document-operations/rotate-pages.md" >}}) and [Change Page Orientation]({{< ref "merger/python-net/developer-guide/single-document-operations/change-page-orientation.md" >}}). |
| **Password Security** | Add, update, remove, or check document passwords without opening the document in an editor. See [Security Operations]({{< ref "merger/python-net/developer-guide/security-operations" >}}). |
| **Page Preview** | Generate PNG, JPEG, or BMP thumbnail images of individual document pages. See [Page Preview]({{< ref "merger/python-net/developer-guide/page-preview.md" >}}). |
| **Document Inspection** | Read file type, page count, page dimensions, and other metadata without modifying the document. See [Get Document Information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}}). |

## Quick Example

{{< tabs "product-overview-quick-example" >}}
{{< tab "merge_pdf_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_pdf_documents():
    # Load the first PDF as the merge base
    with Merger("./input.pdf") as merger:
        # Append the second PDF
        merger.join("./input2.pdf")
        # Save the merged PDF
        merger.save("./output.pdf")

if __name__ == "__main__":
    merge_pdf_documents()
```
{{< /tab >}}
{{< tab "With options" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import PageJoinOptions, PdfJoinOptions

def merge_pdf_with_options():
    # Load the first PDF as the merge base
    with Merger("./input.pdf") as merger:
        # Append only pages 1 and 3 from the second PDF
        merger.join("./input2.pdf", PageJoinOptions([1, 3]))

        # Append a third PDF and preserve its bookmarks
        pdf_join = PdfJoinOptions()
        pdf_join.use_bookmarks = True
        merger.join("./input3.pdf", pdf_join)

        # Save the result
        merger.save("./output.pdf")

if __name__ == "__main__":
    merge_pdf_with_options()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/product-overview/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Where to next

1. **Install the package** — [Installation]({{< ref "merger/python-net/getting-started/installation.md" >}}) walks through PyPI and offline wheel installation for Windows, Linux, and macOS.
2. **Run your first example** — [Quick Start Guide]({{< ref "merger/python-net/getting-started/quick-start-guide" >}}) merges, extracts pages, and splits a document in under five minutes.
3. **Explore runnable examples** — [How to Run Examples]({{< ref "merger/python-net/getting-started/how-to-run-examples.md" >}}) clones the GitHub repository and runs every documented scenario locally or in Docker.
4. **Use it in depth** — the [Developer Guide]({{< ref "merger/python-net/developer-guide" >}}) covers every API surface with runnable, copy-paste code examples.
5. **Plug it into AI pipelines** — [Agents and LLM Integration]({{< ref "merger/python-net/agents-and-llm-integration" >}}) explains the MCP server, `AGENTS.md`, and how to build AI-driven document assembly pipelines.
