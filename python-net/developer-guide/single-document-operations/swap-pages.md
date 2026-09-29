---
id: swap-pages
url: merger/python-net/swap-pages
title: Swap pages
linkTitle: Swap pages
weight: 5
description: "This article explains how to swap two document pages within PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for Python via .NET."
keywords: Swap document pages, Change document pages position, Rearrange document pages, Swap PDF pages, Swap Word document pages, Swap Excel worksheets, Rearrange PDF pages, SwapOptions, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you swap the positions of any two pages within a document. The result is a new document where the two specified pages have exchanged positions — all other pages remain in their original order. The swap is configured through [SwapOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/swapoptions/).

Here are the steps to swap document pages:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source document.
- Create a [SwapOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/swapoptions/) object with the two 1-based page numbers to exchange.
- Call `merger.swap_pages()` passing the `SwapOptions` object.
- Call `merger.save()` to write the resulting document.

{{< tabs "swap-pages-example" >}}
{{< tab "swap_pages.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import SwapOptions

def swap_document_pages():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Swap page 1 and page 3 — they will exchange positions in the output
        merger.swap_pages(SwapOptions(1, 3))
        # Save the document with the pages swapped
        merger.save("./output.pdf")

if __name__ == "__main__":
    swap_document_pages()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/swap-pages/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 336 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/swap-pages/swap_document_pages/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source document**: `Merger("./input.pdf")` opens the document as a context manager, ensuring resources are released on exit.
- **`SwapOptions(1, 3)`**: takes two 1-based page numbers. After the operation, page 1 moves to position 3 and page 3 moves to position 1.
- **`merger.swap_pages()`**: applies the swap in memory. The original file is not modified.
- **`merger.save("./output.pdf")`**: writes the resulting document with the pages in their new order.

{{< alert style="tip" >}}
To move a single page to a specific position without swapping, use [Move page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page" >}}) instead.
{{< /alert >}}

### API reference

- [SwapOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/swapoptions/)
- [Merger.swap_pages()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Move page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page" >}})
- [Remove pages]({{< ref "merger/python-net/developer-guide/single-document-operations/remove-pages" >}})
- [Extract pages]({{< ref "merger/python-net/developer-guide/single-document-operations/extract-pages" >}})
