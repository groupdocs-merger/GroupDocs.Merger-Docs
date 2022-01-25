---
id: swap-pages
url: merger/net/swap-pages
title: Swap pages
weight: 5
description: "This article explains how to rearrange document pages for PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for .NET."
keywords: Swap document pages, Change document pages position, Rearrange document pages, Swap PDF pages, Swap Word document pages, Swap Excel worksheets, Rearrange PDF pages
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** allows to swap two pages positions within the source document. The result is a new document where two pages have their positions exchanged.

Here are the steps to swap document pages:
*   Initialize [SwapOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/swapoptions) class with page numbers to swap;
*   Instantiate [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) object with source document path or stream;
*   Call [SwapPages](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger/methods/swappages) method and pass [SwapOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/swapoptions) object to it;
*   Call [Save](https://apireference.groupdocs.com/net/merger/groupdocs.merger.merger/save/methods/1) method specifying file path to save resultant document.

The following code sample demonstrates how to split document:

```csharp
string filePath = @"c:\sample.pptx";
string filePathOut = @"c:\output\result.pptx";

int pageNumber1 = 3;
int pageNumber2 = 6;
SwapOptions swapOptions = new SwapOptions(pageNumber2, pageNumber1);

using (Merger merger = new Merger(filePath))
{
    merger.SwapPages(swapOptions);
    merger.Save(filePathOut);
}
```
