---
id: extract-pages
url: merger/java/extract-pages
title: Extract pages
weight: 6
description: "Following this guide you will learn how to extract pages from PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for Java."
keywords: Extract page from PDF, Extract page from Word, Extract worksheet from Excel, Extract slide from PowerPoint, Extract document pages
productName: GroupDocs.Merger for Java
hideChildren: False
---
## Extract pages 

[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to extract pages from source document. The result is a new document that contains only specified pages from the source document.

Here are the steps to extract document pages:

*   Initialize [ExtractOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/ExtractOptions) class with page numbers that should appear in the resultant document;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [extractPages](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#extractPages(com.groupdocs.merger.domain.options.interfaces.IExtractOptions)) method and pass [ExtractOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/ExtractOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to extract document pages **by specifying exact page numbers**:

```java
String filePath = "c:\sample.pdf";
String filePathOut = "c:\output\result.pdf";

ExtractOptions extractOptions = new ExtractOptions(new int[] { 1, 4 }); // Resultant document will contain pages 1 and 4

Merger merger = new Merger(filePath);
merger.extractPages(extractOptions);
merger.save(filePathOut);
```

The following code sample demonstrates how to extract document pages **by specifying page numbers range**:

```java
String filePath = "c:\sample.pdf";
String filePathOut = "c:\output\result.pdf";

ExtractOptions extractOptions = new ExtractOptions(1, 3, RangeMode.EvenPages); // Resultant document will contain page 2

Merger merger = new Merger(filePath);
merger.extractPages(extractOptions);
merger.save(filePathOut);
```
