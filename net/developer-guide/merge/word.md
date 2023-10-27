---
id: merge-wordprocessing
url: merger/net/merge/word
title: Merge Word Documents
linkTitle: Merge Word documents
description: "Learn this article and check how to merge Microsoft Office Word documents in .NET applications using C# programming language."
keywords: Merge Word files, Combine DOCX files, Merge DOC files
productName: GroupDocs.Merger for .NET
weight: 40
hideChildren: True
toc: True
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge DOCX files in C#
    appDescription: Merge DOCX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge DOCX files in C# 
        description: Learn how to merge DOCX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source DOCX files 
          text: Create an instance of Merger class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other DOCX files
          text: Add other DOCX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge DOCX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant DOCX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

A word processing file contains user information in plain text or rich text format. A **plain text** file format contains unformatted text and no font or page settings can be applied. In contrast, a **rich text** file format allows formatting options such as setting fonts type, styles (bold, italic, underline, etc.), page margins, headings, bullets and numbers, and several other formatting features. The use of plain text files have reduced significantly with passage of time as there are more powerful computers and programs available to offer rich text files processing.

Common plain text file extensions and associated file formats include **TXT**, **CSV**, while file extensions for rich text documents include **DOCX**, **DOC** and **RTF**.
  
## How to merge DOCX documents

DOCX is a well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. DOCX files can be opened with Word 2007 and lateral versions, but not with the earlier versions of MS Word which support DOC file extensions

Below is code snippet in C# that demonstrates how to merge DOCX files into single file.

```csharp
// Load the source DOCX file
using (Merger merger = new Merger(@"c:\sample1.docx"))
{
    // Add another DOCX file to merge
    merger.Join(@"c:\sample2.docx");
    // Merge DOCX files and save result
    merger.Save(@"c:\merged.docx");
}
```
  
## How to merge Word documents without starting from a new page

There is an additional option for Word document joining that allows to merge those documents without page breaking between them, i.e. the last page of the initial document will be merged with the first page of the next document as one page.

Below is code snippet in C# that demonstrates how to merge DOC files into single file without starting from a new page.

```csharp
// Load the source DOC file
using (Merger merger = new Merger(@"c:\sample1.doc"))
{
    // Define Word join options
    WordJoinOptions joinOptions = new WordJoinOptions();
    joinOptions.Mode = WordJoinMode.Continuous;
    // Add another DOC file to merge
    merger.Join(@"c:\sample2.doc", joinOptions);
    // Merge DOC files and save result
    merger.Save(@"c:\merged.doc");
}
```

## How to merge TXT files

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by a sequence of characters.

You can combine any number of text files like shows this C# code sample:

```csharp
// Load the source TXT file
using (Merger merger = new Merger(@"c:\sample1.txt"))
{
    // Add another TXT file to merge
    merger.Join(@"c:\sample2.txt");
    // Merge TXT files and save result
    merger.Save(@"c:\merged.txt");
}
```

## How to merge RTF files

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

Joining multiple RTF documents into one is pretty the same as for any other formats - just specify files you want to merge and save the resultant document.

```csharp
// Load the source RTF file
using (Merger merger = new Merger(@"c:\sample1.rtf"))
{
    // Add another RTF file to merge
    merger.Join(@"c:\sample2.rtf");
    // Merge RTF files and save result
    merger.Save(@"c:\merged.rtf");
}
```

### Code Examples

Please find more [use-cases and complete C# sources](https://docs.groupdocs.com/merger/net/showcases/) of our backend and frontend examples and try them for free!

### Merge Word files Live Demo

GroupDocs.Merger for .NET provides an online [**Word Merger App**](https://products.groupdocs.app/merger/word), which allows you to try it for free and check its quality and accuracy.
