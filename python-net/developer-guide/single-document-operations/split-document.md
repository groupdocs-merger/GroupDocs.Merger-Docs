---
id: split-document
url: merger/python-net/split-document
title: Split document
linkTitle: Split document
weight: 3
description: "This guide describes how to split a document of PDF, Word, Excel, PowerPoint and many other formats into several resultant documents using GroupDocs.Merger for Python via .NET API."
keywords: Split document, Split PDF, Split Word, Split DOC, Split Presentation, Split Excel, SplitOptions, SplitMode, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you split a single source document into multiple output files. You can split by exact page numbers or by page intervals, and optionally filter to odd or even pages only — all controlled through [SplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/splitoptions/).

Here are the steps to split a document:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source document.
- Create a [SplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/splitoptions/) object with the output file path format (use `{0}` as the file index placeholder) and the desired page numbers.
- Call `merger.split()` passing the `SplitOptions` object. Each output file is written immediately.

{{< tabs "split-document-example" >}}
{{< tab "split_document.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import SplitOptions, SplitMode

def split_document():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Split into separate one-page files for pages 1, 2, and 3
        # Output files: page_0.pdf (page 1), page_1.pdf (page 2), page_2.pdf (page 3)
        merger.split(SplitOptions("./page_{0}.pdf", [1, 2, 3]))

def split_document_by_interval():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Split into multi-page files using page boundaries [2, 4]
        # INTERVAL mode: pages 1 → part_0.pdf, pages 2-3 → part_1.pdf, pages 4+ → part_2.pdf
        merger.split(SplitOptions("./part_{0}.pdf", [2, 4], split_mode=SplitMode.INTERVAL))

if __name__ == "__main__":
    split_document()
    split_document_by_interval()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/split-document/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "split-document-outputs.zip" >}}  
```text
page_1.pdf (84 KB)
page_2.pdf (84 KB)
page_3.pdf (84 KB)
part_0.pdf (84 KB)
part_1.pdf (167 KB)
part_2.pdf (168 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/split-document/split_document/split-document-outputs.zip)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source document**: `Merger("./input.pdf")` opens the document as a context manager, ensuring resources are released automatically.
- **Split by exact pages** (`SplitOptions("./page_{0}.pdf", [1, 2, 3])`): the default mode is `SplitMode.PAGES`, which produces one output file per listed page number. Page numbers are 1-based.
- **Split by interval** (`SplitOptions(..., [2, 4], split_mode=SplitMode.INTERVAL)`): the listed numbers are treated as interval boundaries. Pages before the first boundary form the first segment, pages between each pair of boundaries form subsequent segments, and pages after the last boundary form the final segment.
- **Output format**: the `{0}` placeholder in the path format is replaced with a zero-based file index for each output file.
- No explicit `merger.save()` call is needed — `split()` writes output files directly.

{{< alert style="tip" >}}
To extract only even or odd pages from a range, use the `SplitOptions` overload that accepts `start_number`, `end_number`, and `mode=RangeMode.ODD_PAGES` (or `RangeMode.EVEN_PAGES`).
{{< /alert >}}

### API reference

- [SplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/splitoptions/)
- [SplitMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/splitmode/)
- [RangeMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rangemode/)
- [Merger.split()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Split text file]({{< ref "merger/python-net/developer-guide/single-document-operations/split-text-file" >}})
- [Extract pages]({{< ref "merger/python-net/developer-guide/single-document-operations/extract-pages" >}})
- [Remove pages]({{< ref "merger/python-net/developer-guide/single-document-operations/remove-pages" >}})
