---
id: merge-wordprocessing
url: merger/net/merge/word
title: Merge Word Documents
linkTitle: Merge Word documents
description: "Learn this article and check how to merge Microsoft Office Word documents in .NET applications using C# programming language."
keywords: Merge Word files, Combine DOCX files, Merge DOC files
productName: GroupDocs.Merger for .NET
weight: 2
hideChildren: True
toc: True
---

A word processing file contains user information in plain text or rich text format. A **plain text** file format contains unformatted text and no font or page settings can be applied. In contrast, a **rich text** file format allows formatting options such as setting fonts type, styles (bold, italic, underline, etc.), page margins, headings, bullets and numbers, and several other formatting features. The use of plain text files have reduced significantly with passage of time as there are more powerful computers and programs available to offer rich text files processing.

Common plain text file extensions and associated file formats include **TXT**, **CSV**, while file extensions for rich text documents include **DOCX**, **DOC** and **RTF**.
  
## How to merge DOCX documents

Docx is a well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions, but not with the earlier versions of MS Word which support DOC file extensions

Below is code snippet in C# that demonstrates how to merge DOCX files into single files.

```csharp
// Load the source DOCX file
using (Merger merger = new Merger(@"c:\sample1.docx"))
{
    // Add another DOCX file to merge
    merger.Join(@"c:\sample2.docx");
    // Merge DOCX files ans save result
    merger.Save(@"c:\merged.docx");
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
    // Merge TXT files ans save result
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
    // Merge RTF files ans save result
    merger.Save(@"c:\merged.rtf");
}
```

### Code Examples

Please find more [use-cases and complete C# sources](https://docs.groupdocs.com/merger/net/examples-and-demos/) of our backend and frontend examples and try them for free!

### Merge Word files Live Demo

GroupDocs.Merger for .NET provides an online [**Word Merger App**](https://products.groupdocs.app/merger/word), which allows you to try it for free and check its quality and accuracy.
