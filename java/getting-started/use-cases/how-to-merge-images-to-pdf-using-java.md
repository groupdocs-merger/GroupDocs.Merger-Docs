---
id: how-to-merge-images-to-pdf-using-java
url: merger/java/getting-started/use-cases/how-to-merge-images-to-pdf-using-java
title: How to merge images to PDF using Java
description: "Learn how to merge images to PDF file, combine images into one PDF file programmatically in Java language using GroupDocs.Merger for Java library."
keywords: Merge images to PDF file in Java, Combine images to PDF file programmatically
productName: GroupDocs.Merger for Java
weight: 8
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge images to PDF file in Java
    appDescription: Merge PDF in a quick and efficient way using Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge images to PDF file in Java 
        description: Learn how to merge images to PDF file in Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-java
        steps:
        - name: Load source PDF files 
          text: Create an instance of Merger class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other image files
          text: Add other image files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PDF and image files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PDF file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## PDF Merger Java API

[com.groupdocs.merger](https://products.groupdocs.com/merger/java) allows developers to combine multiple image documents in the preferred order and save them as a single PDF file.

## About PDF File Format

Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/java) to download API jar package and add it to the .pom file. :
```java
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-merger</artifactId>
    <version>23.2</version>
</dependency>
```

### Source images

!["Sample1.jpg"](/merger/net/images/jpg/sample1.jpg)
!["Sample2.jpg"](/merger/net/images/jpg/sample2.jpg)
!["Sample3.jpg"](/merger/net/images/jpg/sample3.jpg)

### How to merge image files to PDF

The following example demonstrates how to merge image files to PDF file with several lines of Java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. Additionally, pass instance of [LoadOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/loadoptions/) class as a second constructor parameter.
* Add another image file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) method. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and specify the filename for the merged PDF file as parameter.

```java

// Load the source image file
Merger merger = new Merger("c:\sample1.jpeg", new LoadOptions(FileType.PDF))
{
    // Add another image file to merge
    merger.join("c:\sample2.png");
    // Add next image file to merge
    merger.join("c:\sample3.bmp");
    // Merge image files and save PDF result
    merger.save("c:\merged.pdf");
}
```

### Result merged PDF file

!["Merged.pdf"](/merger/net/images/jpg/merged_images_to_pdf.jpg)

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PDF Live Demo

GroupDocs.Merger for Java provides an online [**Image to PDF Merger App**](https://products.groupdocs.app/merger/image-to-pdf), which allows you to try it for free and check its quality and accuracy.