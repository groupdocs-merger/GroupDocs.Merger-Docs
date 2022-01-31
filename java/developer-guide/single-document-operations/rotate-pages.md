---
id: rotate-pages
url: merger/java/rotate-pages
title: Rotate pages
weight: 8
description: "Following this guide you will learn how to change PDF document page rotation angle using GroupDocs.Merger for Java API."
keywords: Rotate PDF pages, Rotate document pages, Change PDF page rotation angle
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to change page rotation angle by setting it to 90, 180 or 270 degrees for specific or all document pages.  
Here are the steps to change page rotation:

*   Initialize [RotateOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/RotateOptions) class with desired rotation angle and page numbers;
*   Instantiate [Merger](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [rotatePages](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#rotatePages(com.groupdocs.merger.domain.options.interfaces.IRotateOptions)) method and pass [RotateOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/RotateOptions) object to it;
*   Call [save](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to change page rotation:

```java
String filePath = "c:\sample.pdf";
String filePathOut = "c:\output\result.pdf";

RotateOptions rotateOptions = new RotateOptions(RotateMode.Rotate180, new int[] { 2, 3 });

Merger merger = new Merger(filePath);
merger.rotatePages(rotateOptions);
merger.save(filePathOut);
```
