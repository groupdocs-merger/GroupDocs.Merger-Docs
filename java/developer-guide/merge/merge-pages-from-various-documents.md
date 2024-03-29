---
id: merge-pages-from-various-documents
url: merger/java/merge-pages-from-various-documents
title: Merge pages from various documents
weight: 100
description: "This article explains how to merge some pages from different documents into single PDF, DOCX, Excel or PowerPoint document using GroupDocs.Merger for Java."
keywords: Merge PDF pages into one PDF document, Combine document pages into single document, Merge pages into document using GroupDocs.Merger for Java
productName: GroupDocs.Merger for Java
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** allows to merge the source document with specific document pages from joined document into one resultant document by specifying desired page numbers or page ranges. Joined documents should be of the same format.

Here are the steps to join several document parts:

* Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
* Instantiate [JoinOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/JoinOptions) object and specify desired page numbers or page range to join;
* Call [join](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.lang.String,%20com.groupdocs.merger.domain.options.interfaces.IJoinOptions)) method and pass joined document file path or InputStream to it specifying [JoinOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/JoinOptions) object as parameter. Repeat this step for every joined document part.
* Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to join document parts:

```java
String filePath = "c:\sample.docx";
String filePath2 = "c:\sample2.docx";
String filePathOut = "c:\output\result.docx";

JoinOptions joinOptions = new JoinOptions(1, 2);

Merger merger = new Merger(filePath);
merger.join(filePath2 , joinOptions);
merger.save(filePathOut);
```
