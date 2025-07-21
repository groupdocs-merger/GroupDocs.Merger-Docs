---
id: swap-pages
url: merger/nodejs-java/swap-pages
title: Swap pages
weight: 5
description: "This article explains how to rearrange document pages for PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for Node.js via Java."
keywords: Swap document pages, Change document pages position, Rearrange document pages, Swap PDF pages, Swap Word document pages, Swap Excel worksheets, Rearrange PDF pages
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/nodejs-java) allows to swap two pages positions within the source document. The result is a new document where two pages have their positions exchanged.

Here are the steps to swap document pages:

*   Initialize [SwapOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/SwapOptions) class with page numbers to swap;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [swapPages](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#swapPages(com.groupdocs.merger.domain.options.interfaces.ISwapOptions)) method and pass [SwapOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/SwapOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to split document:

```js
const inputFilePath = `c:/sample.pptx`;
const merger = new groupdocs.merger.Merger(inputFilePath);
const outputPath = `c:/output/result.pptx`;
const swapOptions = new groupdocs.merger.SwapOptions(1, 3);
merger.swapPages(swapOptions);
merger.save(outputPath);
```
