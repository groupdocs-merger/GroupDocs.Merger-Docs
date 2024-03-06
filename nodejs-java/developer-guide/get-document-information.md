---
id: get-document-information
url: merger/nodejs-java/get-document-information
title: Get document information
weight: 2
description: "This article explains how to detect document file type and calculate pages count when merge PDF, Word(DOC, DOCX), Excel(XLS, XLSX), PowerPoint(PPT, PPTX) files with GroupDocs.Merger for Node.js via Java."
keywords: Word, DOC, DOCX, Excel, XLS, XLSX, PowerPoint, PPT, PPTX
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/nodejs-java) allows to get document information which includes:

*   [FileType](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.result/IDocumentInfo#getType())
*   [PageCount](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.result/IDocumentInfo#getPageCount())
*   [Page info ](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.result/IPageInfo)for each document page.

  
The following code sample demonstrates how to get document information.

```java
const merger = new groupdocs.merger.Merger('c:/sample.vsdx');
const documentInformation = merger.getDocumentInfo();
const documentType = documentInformation.getType();
console.log(`Document info file format: ${documentType.getFileFormat()}`);
console.log(`Document info page count: ${documentInformation.getPageCount()}`);
```
