---
id: merge-pdf
url: merger/java/merge-pdf
title: Merge PDF
description: "Follow this guide and learn how to merge PDF files, combine several PDFs into one using GroupDocs.Merger for Java API and couple lines of code"
keywords: Merge PDF, Combine PDF, Join PDF, Merge PDF with GroupDocs.Merger for Java
productName: GroupDocs.Merger for Java
weight: 1
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge PDF files in Java
    appDescription: Merge PDF in a quick and efficient way using Java language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PDF files in Java 
        description: Learn how to merge PDF files in Java language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-java
        steps:
        - name: Load source PDF files 
          text: Create an instance of Merger class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/java/images/merge-files-step-1.png
          imageHeight: 159
          imageWidth: 603
        - name: Add other PDF files
          text: Add other PDF files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/java/images/merge-files-step-2.png
          imageHeight: 159
          imageWidth: 603
        - name: Merge PDF files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PDF file as parameter.
          imageUrl: merger/java/images/merge-files-step-3.png
          imageHeight: 159
          imageWidth: 603
---

## How to merge PDF files in Java

**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)**  allows developers to merge PDF files when it's needed to organize multiple
 PDF files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine PDF documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge PDF files with several lines of Java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PDF file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream)) method. Repeat this step for other PDF documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and specify the filename for the merged PDF file as parameter.

```java
// Load the source PDF file
Merger merger = new Merger("c:\sample1.pdf")

// Add another PDF file to merge
merger.join("c:\sample2.pdf");
// Merge PDF files and save result
merger.save("c:\merged.pdf");
```

### About PDF File Format

Portable Document Format (PDF) is a type of document created by Adobe back in the 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PDF Live Demo

GroupDocs.Merger for Java provides an online [**PDF Merger App**](https://products.groupdocs.app/merger/pdf), which allows you to try it for free and check its quality and accuracy.

[!["Merge PDF"](/merger/java/images/merge/merge-pdf.png)](https://products.groupdocs.app/merger/pdf)