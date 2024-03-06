---
id: supported-document-formats
url: merger/nodejs-java/supported-document-formats
title: Get supported document formats
weight: 1
description: "This article explains how to obtain supported file formats list when merge PDF, Word(DOC, DOCX), Excel(XLS, XLSX), PowerPoint(PPT, PPTX) documents with GroupDocs.Merger within your Node.js via Java applications."
keywords: Word, DOC, DOCX, Excel, XLS, XLSX, PowerPoint, PPT, PPTX
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/nodejs-java) allows to get the list of all [supported file types]({{< ref "merger/nodejs-java/getting-started/supported-document-formats.md" >}}) by following the below steps:
*   Call [getSupportedFileTypes](https://reference.groupdocs.com/nodejs-java/merger/com.groupdocs.merger.domain/FileType#getSupportedFileTypes()) method of [FileType](https://reference.groupdocs.com/nodejs-java/merger/com.groupdocs.merger.domain/FileType) class;
*   Enumerate through the collection of [FileType](https://reference.groupdocs.com/nodejs-java/merger/com.groupdocs.merger.domain/FileType) objects.

The following code sample demonstrates how to get supported file formats list.

```java
const supportedFileTypes = groupdocs.merger.FileType.getSupportedFileTypes().toArray();

supportedFileTypes.forEach((fileType) => {
    console.log('\n' + fileType.getExtension());
});
```
