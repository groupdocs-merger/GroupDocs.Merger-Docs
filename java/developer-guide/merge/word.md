---
id: word
url: merger/java/merge/word
title: Merge Word documents
linkTitle: Merge Word documents
description: "Follow this guide and learn how to merge Word documents, combine several DOCX or DOC files into one using GroupDocs.Merger for Java."
keywords: Merge Word, Merge DOCX, Merge DOC, Join DOCX, Combine DOC with GroupDocs.Merger for Java
productName: GroupDocs.Merger for Java
weight: 2
hideChildren: True
toc: True
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

A word processing file contains user information in plain text or rich text format. A **plain text** file format contains unformatted text and no font or page settings can be applied. In contrast, a **rich text** file format allows formatting options such as setting fonts type, styles (bold, italic, underline, etc.), page margins, headings, bullets and numbers, and several other formatting features. The use of plain text files have reduced significantly with passage of time as there are more powerful computers and programs available to offer rich text files processing.

Common plain text file extensions and associated file formats include **TXT**, **CSV**, while file extensions for rich text documents include **DOCX**, **DOC** and **RTF**.
  
## How to merge DOCX documents

Docx is a well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions, but not with the earlier versions of MS Word which support DOC file extensions

Below is code snippet in java that demonstrates how to merge DOCX files into single file.

```java
// Load the source DOCX file
Merger merger = new Merger("c:\sample1.docx")

// Add another DOCX file to merge
merger.join("c:\sample2.docx");
// Merge DOCX files and save result
merger.save("c:\merged.docx");
```
  
## How to merge Word documents without starting from a new page

There is an additional option for Word document joining that allows to merge those documents without page breaking between them, i.e. the last page of the initial document will be merged with the first page of the next document as one page.

Below is code snippet in java that demonstrates how to merge DOC files into single file without starting from a new page.

```java
// Load the source DOC file
Merger merger = new Merger("c:\sample1.doc")

// Define Word join options
WordJoinOptions joinOptions = new WordJoinOptions();
joinOptions.setMode(WordJoinMode.Continuous);
// Add another DOC file to merge
merger.join("c:\sample2.doc", joinOptions);
// Merge DOC files and save result
merger.save("c:\merged.doc");
```

## How to merge TXT files

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by a sequence of characters.

You can combine any number of text files like shows this java code sample:

```java
// Load the source TXT file
Merger merger = new Merger("c:\sample1.txt")

// Add another TXT file to merge
merger.join("c:\sample2.txt");
// Merge TXT files and save result
merger.save("c:\merged.txt");
```

## How to merge RTF files

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

Joining multiple RTF documents into one is pretty the same as for any other formats - just specify files you want to merge and save the resultant document.

```java
// Load the source RTF file
Merger merger = new Merger("c:\sample1.rtf"))

// Add another RTF file to merge
merger.join("c:\sample2.rtf");
// Merge RTF files and save result
merger.save("c:\merged.rtf");
```

## How to merge DOCX streams

Please read the following article: [How to properly merge DOCX streams]({{< ref "merger/java/getting-started/use-cases/how-to-properly-merge-documents-using-java.md" >}})

### Code Examples

Please find more [use-cases and complete Java sources](https://docs.groupdocs.com/merger/java/showcases/) of our backend and frontend examples and try them for free!

### Merge Word files Live Demo

GroupDocs.Merger for Java provides an online [**Word Merger App**](https://products.groupdocs.app/merger/word), which allows you to try it for free and check its quality and accuracy.