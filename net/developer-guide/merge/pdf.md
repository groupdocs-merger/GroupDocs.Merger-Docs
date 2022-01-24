---
id: merge-pdf
url: merger/net/merge/pdf
title: Merge PDF
description: "Learn how to merge PDF files, combine PDF files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge PDF files in C#, Combine PDF files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge PDF files in C#
    appDescription: Merge PDF in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PDF files in C# 
        description: Learn how to merge PDF files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source PDF files 
          text: Create an instance of Merger class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other PDF files
          text: Add other PDF files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PDF files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PDF file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge PDF files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge PDF files when it's needed to organize multiple
 PDF files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine PDF documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge PDF files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PDF file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other PDF documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged PDF file as parameter.

```csharp
// Load the source PDF file
using (Merger merger = new Merger(@"c:\sample1.pdf"))
{
    // Add another PDF file to merge
    merger.Join(@"c:\sample2.pdf");
    // Merge PDF files ans save result
    merger.Save(@"c:\merged.pdf");
}
```

### About PDF File Format 

Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge PDF Live Demo 

GroupDocs.Merger for .NET provides an online [**PDF Merger App**](https://products.groupdocs.app/merger/pdf), which allows you to try it for free and check its quality and accuracy.

[!["Merge PDF"](merger/net/images/merge/merge-pdf.png)](https://products.groupdocs.app/merger/pdf)