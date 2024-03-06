---
id: remove-pages
url: merger/nodejs-java/remove-pages
title: Remove pages
weight: 2
description: "Follow this guide and learn how to remove page from PDF or Word document, delete worksheet from Excel file or remove slides from PowerPoint presentations with GroupDocs.Merger for Java API."
keywords: Remove page from document, Delete page from document, Remove page, Delete page
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/nodejs-java) provides an ability to remove single page or a collection of specific page numbers from the source document.   
Here are the steps to remove document page(s):

*   Initialise [RemoveOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/RemoveOptions) class with page numbers to remove;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or stream;
*   Call [removePages](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#removePages(com.groupdocs.merger.domain.options.interfaces.IRemoveOptions)) method and pass [RemoveOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/RemoveOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method and pass desired file path to save resultant document.

The following code sample demonstrates how to remove document pages:

```java
const inputFilePath = `c:/sample.one`;
const merger = new groupdocs.merger.Merger(inputFilePath);
const outputPath = `c:/output/result.one`;
const removeOptions = new groupdocs.merger.RemoveOptions(1, 2);
merger.removePages(removeOptions);
merger.save(outputPath);
```
