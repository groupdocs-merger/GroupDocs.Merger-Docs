---
id: presentation
url: merger/java/merge-presentation
title: Merge Presentation
weight: 2
description: "This article explains how to merge PowerPoint presentations, combine several PPTX or PPT files into one using GroupDocs.Merger for Java API and couple lines of code."
keywords: Merge PowerPoint, Merge Presentations, Merge PPT, Merge PPTX, Merge PPSX, Merge PPS, Join PowerPoint, Combine PowerPoint with GroupDocs.Merger for Java
productName: GroupDocs.Merger for Java
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge PPTX files in Java
    appDescription: Merge PPTX in a quick and efficient way using Java language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PPTX files in Java 
        description: Learn how to merge PPTX files in Java language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-java
        steps:
        - name: Load source PPTX files 
          text: Create an instance of Merger class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/java/images/merge-files-step-1.png
          imageHeight: 159
          imageWidth: 603
        - name: Add other PPTX files
          text: Add other PPTX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/java/images/merge-files-step-2.png
          imageHeight: 159
          imageWidth: 603
        - name: Merge PPTX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PPTX file as parameter.
          imageUrl: merger/java/images/merge-files-step-3.png
          imageHeight: 159
          imageWidth: 603
---

## How to merge PPTX presentations

**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** exposes powerful and easy to use API to merge PowerPoint and Open Document presentations of PPT, PPTX, PPS, PPSX and ODP, OTP formats. Presentations can be combined as a whole or on a page by page basis depending on your requirements. The big advantage of GroupDocs.Merger is that presentations can be merged programmatically without any third-party software installed (like Microsoft PowerPoint or Open Office) or manual work.  
GroupDocs.Merger combines presentations with all their content with no quality and data loss - text formatting, comments, animations, smart arts, shapes, etc.  
  
GroupDocs.Merger API provides different overloads of [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.lang.String)) method to combine additional files with the source document loaded into [Merger](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object. 

* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.lang.String))([String](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html?is-external=true "class or interface in java.lang")) - allows to merge document provided via file path on a local disk; 
* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.io.InputStream))([InputStream](http://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html?is-external=true "class or interface in java.io")) - provides an ability to combine documents loaded from any source - memory stream, remote URL etc.;
* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.lang.String,%20com.groupdocs.merger.domain.options.interfaces.IJoinOptions))([String](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html?is-external=true "class or interface in java.lang"), [IJoinOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options.interfaces/IJoinOptions "interface in com.groupdocs.merger.domain.options.interfaces")) - is used for merging specific pages for document stored at local disk; 
* [join](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#join(java.io.InputStream,%20com.groupdocs.merger.domain.options.interfaces.IJoinOptions))([InputStream](http://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html?is-external=true "class or interface in java.io"), [IJoinOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options.interfaces/IJoinOptions "interface in com.groupdocs.merger.domain.options.interfaces")) - used for merging specific pages from document provided as a stream.

The following example demonstrates how to merge presentations with several lines of code:

```java
Merger merger = new Merger(@"c:\presentation1.pptx"); 
merger.join(@"c:\presentation2.pptx");
merger.save(@"c:\merged.pptx");
```

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!