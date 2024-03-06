---
id: extract-pages
url: merger/nodejs-java/extract-pages
title: Extract pages
weight: 6
description: "Following this guide you will learn how to extract pages from PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for Node.js via Java."
keywords: Extract page from PDF, Extract page from Word, Extract worksheet from Excel, Extract slide from PowerPoint, Extract document pages
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
---
## Extract pages 

[**GroupDocs.Merger**](https://products.groupdocs.com/merger/nodejs-java) allows to extract pages from source document. The result is a new document that contains only specified pages from the source document.

Here are the steps to extract document pages:

*   Initialize [ExtractOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/ExtractOptions) class with page numbers that should appear in the resultant document;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [extractPages](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#extractPages(com.groupdocs.merger.domain.options.interfaces.IExtractOptions)) method and pass [ExtractOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/ExtractOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to extract document pages **by specifying exact page numbers**:

```java
const inputFilePath = `c:/sample.pdf`;
const merger = new groupdocs.merger.Merger(inputFilePath);
const outputPath = `c:/output/result.pdf`;
const java = require('java');
const pageArray = java.newArray('int', [1, 3]);
const extractOptions = new groupdocs.merger.ExtractOptions(pageArray);
merger.extractPages(extractOptions);
merger.save(outputPath);
```

The following code sample demonstrates how to extract document pages **by specifying page numbers range**:

```java
const inputFilePath = `c:/sample.pdf`;
const merger = new groupdocs.merger.Merger(inputFilePath);
const outputPath = `c:/output/result.pdf`;
const evenPages = groupdocs.merger.RangeMode.EvenPages;
const extractOptions = new groupdocs.merger.ExtractOptions(1, 3, evenPages);
merger.extractPages(extractOptions);
merger.save(outputPath);
```
