---
id: rotate-pages
url: merger/nodejs-java/rotate-pages
title: Rotate pages
weight: 8
description: "Following this guide you will learn how to change PDF document page rotation angle using GroupDocs.Merger for Node.js via Java API."
keywords: Rotate PDF pages, Rotate document pages, Change PDF page rotation angle
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/nodejs-java) allows to change page rotation angle by setting it to 90, 180 or 270 degrees for specific or all document pages.  
Here are the steps to change page rotation:

*   Initialize [RotateOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/RotateOptions) class with desired rotation angle and page numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [rotatePages](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#rotatePages(com.groupdocs.merger.domain.options.interfaces.IRotateOptions)) method and pass [RotateOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/RotateOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to change page rotation:

```js
const inputFilePath = `c:/sample.pdf`;
const merger = new groupdocs.merger.Merger(inputFilePath);
const outputPath = `c:/output/result.pdf`;
const rotateMode = groupdocs.merger.RotateMode.Rotate180;
const rotateOptions = new groupdocs.merger.RotateOptions(rotateMode, 1, 2);
merger.rotatePages(rotateOptions);
merger.save(outputPath);
```
