---
id: swap-pages
url: merger/python-net/swap-pages
title: Swap pages
weight: 5
description: "This article explains how to rearrange document pages for PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for Python via .NET."
keywords: Swap document pages, Change document pages position, Rearrange document pages, Swap PDF pages, Swap Word document pages, Swap Excel worksheets, Rearrange PDF pages
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) allows to swap two pages positions within the source document. The result is a new document where two pages have their positions exchanged.

Here are the steps to swap document pages:

*   Initialize [SwapOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/SwapOptions) class with page numbers to swap;
*   Instantiate [Merger](https://reference.groupdocs.com/net/merger/groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [swapPages](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/swappages/) method and pass [SwapOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/SwapOptions) object to it;
*   Call [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method specifying file path to save resultant document.

The following code sample demonstrates how to split document:

```python
with gm.Merger("c:/sample.pptx") as merger:
    swap_options = gm.domain.options.SwapOptions(1, 3)
    merger.swap_pages(swap_options)
    merger.save("c:/result.pptx")
```
