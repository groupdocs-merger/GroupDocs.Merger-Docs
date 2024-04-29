---
id: how-to-properly-merge-documents-using-java
url: merger/java/getting-started/use-cases/how-to-properly-merge-documents-using-java
title: How to properly merge documents using Java
description: "This article describes how to properly merge documents using GroupDocs.Merger for Java product."
keywords: Merge PDF using file paths in Java, Merge DOCX using file streams in Java, Merge PPTX using memory streams in Java
productName: GroupDocs.Merger for Java
weight: 11
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge properly documents in C#
    appDescription: Merge documents in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge documents in C# 
        description: Learn how to merge documents in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source stream 
          text: Create an instance of Merger class and pass source archive file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other stream
          text: Add other stream you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge documents and save result 
          text: Call Merger class Save method and pass the filename for the resultant archive file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---
# with File Paths

The easiest and most reliable way to merge PDF files, using the "GroupDocs.Merger for Java" product, is to use the full paths to these files.

The following example demonstrates how to merge PDF files using file paths in Java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#Merger-java.lang.String-) class and pass the full PDF file path as a constructor parameter.
* Add another PDF file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.lang.String-) method.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.lang.String-) method and specify the filename for the merged PDF file as parameter.

```java
// Load the source PDF file
Merger merger = new Merger("c:\sample1.pdf");

// Add another PDF file to merge
merger.join("c:\sample2.pdf");
// Merge PDF files and save result
merger.save("c:\merged.pdf");

```


# with File Input Streams

There are situations, and quite often, when it is necessary to work with other classes inherited from java.io.InputStream, for example with FileInputStream or others. In this case, it is necessary to use additional parameters to specify the exact file type that is used in this case. Because the "GroupDocs.Merger for Java" product cannot always accurately determine the file type by its stream. Therefore, to avoid exceptions when merging PDF and other files, see the example below:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#Merger-java.io.InputStream-com.groupdocs.merger.domain.options.interfaces.ILoadOptions-) class and pass instance of [LoadOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/loadoptions/) with PPTX file type as a constructor parameter.
* Create an instance of [JoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/joinoptions/) class with PPTX file type as a constructor parameter.
* Add another PPTX stream to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-com.groupdocs.merger.domain.options.interfaces.IJoinOptions-) method and pass instance of [JoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/joinoptions/) class as a method parameter.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.lang.String-) method and specify the filename for the merged PPTX file as parameter.

```java

String filePath1 = "c:/sample1.pptx";
String filePath2 = "c:/sample2.pptx";

FileType fileType1 = FileType.fromExtension(filePath1.substring(filePath1.lastIndexOf('.')));
FileType fileType2 = FileType.fromExtension(filePath2.substring(filePath2.lastIndexOf('.')));

File initialFile1 = new File(filePath1);
InputStream fileStream1 = new FileInputStream(initialFile1);

File initialFile2 = new File(filePath2);
InputStream fileStream2 = new FileInputStream(initialFile2);

// Init Load options with defined FileType
LoadOptions loadOptions = new LoadOptions(fileType1);

// Load the source PPTX stream
Merger merger = new Merger(fileStream1, loadOptions);

// Define join options with PPTX file type
JoinOptions joinOptions = new JoinOptions(fileType2);
// Add another PPTX stream to merge
merger.join(fileStream2, joinOptions);
// Merge PPTX streams and save result
merger.save("c:\merged.pptx");

```

# with File Input Streams for cross-merging

There may also be situations when it is necessary to combine different types of streams into PDF. In this case, you can use the example below:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#Merger-java.io.InputStream-com.groupdocs.merger.domain.options.interfaces.ILoadOptions-) class and pass instance of [LoadOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/loadoptions/) with ini DOCX file type and out PDF one as a constructor parameters.
* Create an instance of [JoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/joinoptions/) class with PPTX file type as a constructor parameter.
* Add another PPTX stream to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-com.groupdocs.merger.domain.options.interfaces.IJoinOptions-) method and pass instance of [JoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/joinoptions/) class as a method parameter.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.lang.String-) method and specify the filename for the merged PDF file as parameter.

```java

String filePath1 = "c:/sample1.docx";
String filePath2 = "c:/sample2.pptx";

File initialFile1 = new File(filePath1);
InputStream fileStream1 = new FileInputStream(initialFile1);

File initialFile2 = new File(filePath2);
InputStream fileStream2 = new FileInputStream(initialFile2);

// Init Load options with defined FileTypes
LoadOptions loadOptions = new LoadOptions(FileType.DOCX, FileType.PDF);

// Load the source DOCX stream as PDF
Merger merger = new Merger(fileStream1, loadOptions);

// Define join options with PPTX file type
JoinOptions joinOptions = new JoinOptions(FileType.PPTX);
// Add another PPTX stream to merge
merger.join(fileStream2, joinOptions);
// Merge document streams and save PDF result
merger.save("c:\merged.pdf");

```
