---
id: merge-docx
url: merger/net/merge/docx
title: Merge DOCX
description: "Learn how to merge DOCX files, combine DOCX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge DOCX files in C#, Combine DOCX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
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

## How to merge DOCX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge DOCX files when it's needed to organize multiple
 DOCX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine DOCX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge DOCX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another DOCX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other DOCX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged DOCX file as parameter.

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

### About DOCX File Format 

Docx is well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions but not with the earlier versions of MS Word which support DOC file extensions.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge DOCX Live Demo 

GroupDocs.Merger for .NET provides an online [**DOCX Merger App**](https://products.groupdocs.app/merger/docx), which allows you to try it for free and check its quality and accuracy.

[!["Merge DOCX"](merger/net/images/merge/merge-docx.png)](https://products.groupdocs.app/merger/docx)