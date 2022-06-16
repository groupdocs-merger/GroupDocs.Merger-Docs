---
id: word
url: merger/java/merge-word-documents
title: Merge Word documents
weight: 3
description: "Follow this guide and learn how to merge Word documents, combine several DOCX or DOC files into one using GroupDocs.Merger for Java."
keywords: Merge Word, Merge DOCX, Merge DOC, Join DOCX, Combine DOC with GroupDocs.Merger for Java
productName: GroupDocs.Merger for Java
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge DOC files in Java
    appDescription: Merge DOC in a quick and efficient way using Java language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge DOC files in Java 
        description: Learn how to merge DOC files in Java language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-java
        steps:
        - name: Load source DOC files 
          text: Create an instance of Merger class and pass source DOC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/java/images/merge-files-step-1.png
          imageHeight: 159
          imageWidth: 603
        - name: Add other DOC files
          text: Add other DOC files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/java/images/merge-files-step-2.png
          imageHeight: 159
          imageWidth: 603
        - name: Merge DOC files and save result 
          text: Call Merger class Save method and pass the filename for the resultant DOC file as parameter.
          imageUrl: merger/java/images/merge-files-step-3.png
          imageHeight: 159
          imageWidth: 603
---

## How to merge DOC documents

**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** provides an easy way to merge Microsoft Word documents of DOC, DOCX, DOCM, DOT, DOTX, DOTM, RTF formats and Open Document formats like ODT, OTT etc. It takes just single line of code to append one document to another preserving all content - page setup, headers and footers, formatting, styles and other content. There is no third-party applications required (like Microsoft Word and Open Office).   
  
GroupDocs.Merger API provides different overloads of [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.lang.String)) method to combine additional files with the source document loaded into [Merger](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object. 

* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.lang.String))([String](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html?is-external=true "class or interface in java.lang")) - allows to merge document provided via file path on a local disk; 
* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.io.InputStream))([InputStream](http://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html?is-external=true "class or interface in java.io")) - provides an ability to combine documents loaded from any source - memory stream, remote URL etc.;
* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.lang.String,%20com.groupdocs.merger.domain.options.interfaces.IJoinOptions))([String](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html?is-external=true "class or interface in java.lang"), [IJoinOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options.interfaces/IJoinOptions "interface in com.groupdocs.merger.domain.options.interfaces")) - is used for merging specific pages for document stored at local disk; 
* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.io.InputStream,%20com.groupdocs.merger.domain.options.interfaces.IJoinOptions))([InputStream](http://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html?is-external=true "class or interface in java.io"), [IJoinOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options.interfaces/IJoinOptions "interface in com.groupdocs.merger.domain.options.interfaces")) - used for merging specific pages from document provided as a stream.

This code sample shows how to merge Microsoft Word documents:

```java
Merger merger = new Merger(@"c:\document1.doc"); 
merger.join(@"c:\document2.doc");
merger.save(@"c:\merged.doc");
```

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!