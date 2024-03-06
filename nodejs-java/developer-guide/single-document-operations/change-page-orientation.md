---
id: change-page-orientation
url: merger/nodejs-java/change-page-orientation
title: Change page orientation
weight: 7
description: "Following this guide you will learn how to change Word document page orientation to Portrait or Landscape using GroupDocs.Merger for Node.js via Java."
keywords: DOCX page orientation, Change Word page orientation, Page Portrait orientation, Page Landscape orientation
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/nodejs-java) allows to set **Portrait** or **Landscape** page orientation for specific or all document pages.

Here are the steps to change page orientation:

*   Initialize [OrientationOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/OrientationOptions) class with desired orientation mode and page numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [changeOrientation](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#changeOrientation(com.groupdocs.merger.domain.options.interfaces.IOrientationOptions)) method and pass [OrientationOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/OrientationOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to change page orientation:

```java
const inputFilePath = `c:/sample.docx`;
const merger = new groupdocs.merger.Merger(inputFilePath);
const outputPath = `c:/output/result.docx`;
const orientationMode = groupdocs.merger.OrientationMode.Landscape;
const orientationOptions = new groupdocs.merger.OrientationOptions(orientationMode, 1, 2);
merger.changeOrientation(orientationOptions);
merger.save(outputPath);
```
