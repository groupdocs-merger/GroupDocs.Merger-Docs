---
id: change-page-orientation
url: merger/java/change-page-orientation
title: Change page orientation
weight: 7
description: "Following this guide you will learn how to change Word document page orientation to Portrait or Landscape using GroupDocs.Merger for Java."
keywords: DOCX page orientation, Change Word page orientation, Page Portrait orientation, Page Landscape orientation
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to set **Portrait** or **Landscape** page orientation for specific or all document pages.

Here are the steps to change page orientation:

*   Initialize [OrientationOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/OrientationOptions) class with desired orientation mode and page numbers;
*   Instantiate [Merger](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [changeOrientation](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#changeOrientation(com.groupdocs.merger.domain.options.interfaces.IOrientationOptions)) method and pass [OrientationOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/OrientationOptions) object to it;
*   Call [save](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to change page orientation:

```java
String filePath = "c:\sample.docx";
String filePathOut = "c:\output\result.docx";

OrientationOptions orientationOptions = new OrientationOptions(OrientationMode.Landscape, new int[] { 3, 4 });

Merger merger = new Merger(filePath);
merger.changeOrientation(orientationOptions);
merger.save(filePathOut);
```
