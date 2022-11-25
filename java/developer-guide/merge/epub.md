---
id: merge-epub
url: merger/java/merge/epub
title: Merge EPUB
description: "Learn how to merge EPUB files, combine EPUB files into one file programmatically in Java language using GroupDocs.Merger for Java library."
keywords: Merge EPUB files in Java, Combine EPUB files programmatically
productName: GroupDocs.Merger for Java
weight: 23
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge EPUB files in Java
    appDescription: Merge EPUB in a quick and efficient way using Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge EPUB files in Java 
        description: Learn how to merge EPUB files in Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source EPUB files 
          text: Create an instance of Merger class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/java/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other EPUB files
          text: Add other EPUB files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/java/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge EPUB files and save result 
          text: Call Merger class Save method and pass the filename for the resultant EPUB file as parameter.
          imageUrl: merger/java/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge EPUB files in Java

You can easily combine multiple EPUB files into one using [GroupDocs.Merger](https://products.groupdocs.com/merger/java) library API and all the files content will be preserved.
The following example demonstrates how to merge EPUB files with several lines of C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another EPUB file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream)) method. Repeat this step for other EPUB documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and specify the filename for the merged EPUB file as parameter.

```java
// Load the source EPUB file
Merger merger = new Merger("c:\sample1.epub")

// Add another EPUB file to merge
merger.join("c:\sample2.epub");
// Merge EPUB files and save result
merger.save("c:\merged.epub");
```

### About EPUB File Format 

Files with .EPUB extension are an e-book file format that provide a standard digital publication format for publishers and consumers. The format has been so common by now that it is supported by many e-readers and software applications. For example, on Mac OS, the pre-installed Books software provides the support for opening such files. In addition, there are a lot of compatible software available for smartphones, tablets and computers.

### Code Examples

Please find more [use-cases and complete java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge EPUB Live Demo 

GroupDocs.Merger for Java provides an online [**EPUB Merger App**](https://products.groupdocs.app/merger/epub), which allows you to try it for free and check its quality and accuracy.

[!["Merge EPUB"](/merger/java/images/merge/merge-epub.png)](https://products.groupdocs.app/merger/epub)