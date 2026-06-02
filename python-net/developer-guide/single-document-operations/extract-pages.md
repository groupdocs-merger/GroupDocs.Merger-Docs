---
id: extract-pages
url: merger/python-net/extract-pages
title: Extract pages
linkTitle: Extract pages
weight: 6
description: "Following this guide you will learn how to extract pages from PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for Python via .NET."
keywords: Extract page from PDF, Extract page from Word, Extract worksheet from Excel, Extract slide from PowerPoint, Extract document pages, ExtractOptions, RangeMode, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you extract selected pages from a source document and save them as a new document. You can specify pages by exact numbers or by a page range with an even/odd filter — all through [ExtractOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/extractoptions/).

Here are the steps to extract document pages:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source document.
- Create an [ExtractOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/extractoptions/) object with the desired page numbers or range.
- Call `merger.extract_pages()` passing the `ExtractOptions` object.
- Call `merger.save()` to write the resulting document.

{{< tabs "extract-pages-example" >}}
{{< tab "extract_pages.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import ExtractOptions, RangeMode

def extract_pages_by_numbers():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Extract pages 2, 4, and 6 into a new document
        merger.extract_pages(ExtractOptions([2, 4, 6]))
        # Save the document that contains only the extracted pages
        merger.save("./output.pdf")

def extract_pages_even_range():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Extract all even-numbered pages between pages 1 and 6 (i.e. pages 2, 4, 6)
        merger.extract_pages(ExtractOptions(
            start_number=1,
            end_number=6,
            mode=RangeMode.EVEN_PAGES,
        ))
        # Save the resulting document
        merger.save("./output.pdf")

if __name__ == "__main__":
    extract_pages_by_numbers()
    extract_pages_even_range()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/extract-pages/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 250 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/extract-pages/extract_pages_by_numbers/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source document**: `Merger("./input.pdf")` opens the document as a context manager, ensuring resources are released on exit.
- **Extract by exact page numbers** (`ExtractOptions([2, 4, 6])`): pass a list of 1-based page numbers. The output document contains those pages in their original order.
- **Extract by range with filter** (`ExtractOptions(start_number=1, end_number=6, mode=RangeMode.EVEN_PAGES)`): specify a start and end page, then use `RangeMode.EVEN_PAGES` or `RangeMode.ODD_PAGES` to select only the matching pages within that range.
- **`merger.extract_pages()`**: the correct Python method name. The equivalent .NET method is `ExtractPages` — do not use `merger.extract()` (it does not exist).
- **`merger.save("./output.pdf")`**: always call `save()` after `extract_pages()` to write the output document.

{{< alert style="tip" >}}
Page numbers are always 1-based. Requesting a page number beyond the document's page count raises an exception.
{{< /alert >}}

### API reference

- [ExtractOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/extractoptions/)
- [RangeMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rangemode/)
- [Merger.extract_pages()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Remove pages]({{< ref "merger/python-net/developer-guide/single-document-operations/remove-pages" >}})
- [Split document]({{< ref "merger/python-net/developer-guide/single-document-operations/split-document" >}})
- [Move page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page" >}})
