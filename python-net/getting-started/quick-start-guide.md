---
id: quick-start-guide
url: merger/python-net/getting-started/quick-start-guide
title: Quick Start Guide
linkTitle: Quick Start Guide
second_title: A simple example of how to use GroupDocs.Merger for Python via .NET
weight: 5
keywords: quick start, hello world, get started, merge DOCX, extract pages, split PDF, pip install, venv, virtual environment, GroupDocs.Merger, python
description: "Set up a virtual environment, install groupdocs-merger-net, and run three minimal examples — merge two DOCX files, extract pages from a PDF, and split a PDF into single pages — in under five minutes."
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

This guide walks you through setting up GroupDocs.Merger for Python via .NET and running three short examples that cover the most common document manipulation scenarios.

## Prerequisites

To proceed, make sure you have:

1. **A configured environment** as described in the [System Requirements]({{< ref "merger/python-net/getting-started/system-requirements.md" >}}) topic.
2. **Optionally** you may [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/) to test all product features without evaluation limits.

## Set Up Your Development Environment

For best practices, use a virtual environment to manage dependencies. Learn more in the [Create and Use Virtual Environments](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments) documentation.

### Create and Activate a Virtual Environment

Create a virtual environment:

{{< tabs "venv-create" >}}
{{< tab "Windows" >}}
```ps
py -m venv .venv
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 -m venv .venv
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m venv .venv
```
{{< /tab >}}
{{< /tabs >}}

Activate the virtual environment:

{{< tabs "venv-activate" >}}
{{< tab "Windows" >}}
```ps
.venv\Scripts\activate
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
source .venv/bin/activate
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
source .venv/bin/activate
```
{{< /tab >}}
{{< /tabs >}}

### Install the `groupdocs-merger-net` Package

After activating the virtual environment, install the latest package version:

{{< tabs "install-pkg" >}}
{{< tab "Windows" >}}
```ps
py -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< /tabs >}}

You should see:

```
Successfully installed groupdocs-merger-net-*
```

## Example 1: Merge Two Documents

The simplest use case — load a base document, append a second document, and save the combined result.

{{< tabs "example1-merge-docx" >}}
{{< tab "merge_two_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_two_documents():
    # Load the first DOCX as the merge base
    with Merger("./input.docx") as merger:
        # Append the second DOCX
        merger.join("./input2.docx")
        # Save the combined document
        merger.save("./output.docx")

if __name__ == "__main__":
    merge_two_documents()
```
{{< /tab >}}
{{< tab "input.docx" >}}
{{< tab-text >}}
`input.docx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/getting-started/quick-start-guide/input.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.docx" >}}
{{< tab-text >}}
`input2.docx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/getting-started/quick-start-guide/input2.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.docx" >}}  
```text
Binary file (DOCX, 8 KB)
```
[Download full output](/merger/python-net/_output_files/getting-started/quick-start-guide/merge_two_documents/output.docx)
{{< /tab >}}
{{< /tabs >}}

Your folder should look like this:

```
demo-app/
 ├── merge_two_documents.py
 ├── input.docx
 └── input2.docx
```

### Run the App

{{< tabs "run-example1" >}}
{{< tab "Windows" >}}
```ps
py merge_two_documents.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 merge_two_documents.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 merge_two_documents.py
```
{{< /tab >}}
{{< /tabs >}}

Check for `output.docx` in the current directory.

### Explanation

- `Merger("./input.docx")` — opens the first document as the merge base inside a context manager that releases resources on exit.
- `merger.join("./input2.docx")` — appends the entire second document after the last page of the first.
- `merger.save("./output.docx")` — writes the combined document to disk.

## Example 2: Extract Specific Pages from a PDF

Use `extract_pages` with an `ExtractOptions` page list to produce a new document containing only the specified pages.

{{< tabs "example2-extract-pages" >}}
{{< tab "extract_pages_from_pdf.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import ExtractOptions

def extract_pages_from_pdf():
    # Load the source PDF
    with Merger("./input.pdf") as merger:
        # Extract pages 1 and 2 into a new document
        merger.extract_pages(ExtractOptions([1, 2]))
        # Save the extracted pages as a new PDF
        merger.save("./output.pdf")

if __name__ == "__main__":
    extract_pages_from_pdf()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/getting-started/quick-start-guide/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 85 KB)
```
[Download full output](/merger/python-net/_output_files/getting-started/quick-start-guide/extract_pages_from_pdf/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Run the App

{{< tabs "run-example2" >}}
{{< tab "Windows" >}}
```ps
py extract_pages_from_pdf.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 extract_pages_from_pdf.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 extract_pages_from_pdf.py
```
{{< /tab >}}
{{< /tabs >}}

### Explanation

- `ExtractOptions([1, 2])` — specifies a 1-based list of page numbers to keep. Pages not in the list are discarded.
- `merger.extract_pages(...)` — filters the loaded document to only the specified pages.
- `merger.save("./output.pdf")` — writes the result (a 2-page PDF) to disk.

You can also use a range with `RangeMode` instead of an explicit list:

```python
from groupdocs.merger.domain.options import ExtractOptions, RangeMode

# Extract all even-numbered pages between page 1 and page 6
merger.extract_pages(ExtractOptions(start_number=1, end_number=6, mode=RangeMode.EVEN_PAGES))
```

## Example 3: Split a Document into Single Pages

Use `split` with a `SplitOptions` page list to write each listed page to its own output file.

{{< tabs "example3-split-pdf" >}}
{{< tab "split_document_pages.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import SplitOptions

def split_document_pages():
    # Load the source PDF
    with Merger("./input.pdf") as merger:
        # Split pages 1, 2, and 3 into separate files
        # {0} in the path format is replaced with the page number
        merger.split(SplitOptions("./page_{0}.pdf", [1, 2, 3]))

if __name__ == "__main__":
    split_document_pages()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/getting-started/quick-start-guide/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "split-document-pages-outputs.zip" >}}  
```text
page_1.pdf (84 KB)
page_2.pdf (84 KB)
page_3.pdf (84 KB)
```
[Download full output](/merger/python-net/_output_files/getting-started/quick-start-guide/split_document_pages/split-document-pages-outputs.zip)
{{< /tab >}}
{{< /tabs >}}

### Run the App

{{< tabs "run-example3" >}}
{{< tab "Windows" >}}
```ps
py split_document_pages.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 split_document_pages.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 split_document_pages.py
```
{{< /tab >}}
{{< /tabs >}}

After running, you will find `page_1.pdf`, `page_2.pdf`, and `page_3.pdf` in the current directory.

### Explanation

- `SplitOptions("./page_{0}.pdf", [1, 2, 3])` — specifies the output file name pattern and the 1-based list of pages to extract. `{0}` is replaced with the page number for each output file.
- `merger.split(...)` — writes one output file per listed page.

## Next Steps

- [Supported File Formats]({{< ref "merger/python-net/getting-started/supported-document-formats.md" >}}) — see the complete list of supported document types.
- [Licensing]({{< ref "merger/python-net/getting-started/licensing-and-subscription.md" >}}) — understand licensing and evaluation limits.
- [Developer Guide]({{< ref "merger/python-net/developer-guide" >}}) — runnable examples for every API feature.
- [Technical Support]({{< ref "merger/python-net/technical-support" >}}) — contact support if you encounter issues.
