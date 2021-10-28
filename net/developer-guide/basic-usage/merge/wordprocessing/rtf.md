---
id: merge-rtf
url: merger/net/merge/rtf
title: Merge RTF
description: "Learn how to merge RTF files, combine RTF files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge RTF files in C#, Combine RTF files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge RTF files in C#
    appDescription: Merge RTF in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge RTF files in C# 
        description: Learn how to merge RTF files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source RTF files 
          text: Create an instance of Merger class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other RTF files
          text: Add other RTF files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge RTF files and save result 
          text: Call Merger class Save method and pass the filename for the resultant RTF file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge RTF files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge RTF files when it's needed to organize multiple
 RTF files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine RTF documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge RTF files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source RTF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another RTF file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other RTF documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged RTF file as parameter.

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

### About RTF File Format 

Introduced and documented by Microsoft, the Rich Text Format (RTF) represents a method of encoding formatted text and graphics for use within applications. The format facilitates cross-platform document exchange with other Microsoft Products, thus serving the purpose of interoperability. This capability makes it a standard of data transfer between word processing software and, hence, contents can be transferred from one operating system to another without losing document formatting.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge RTF Live Demo 

GroupDocs.Merger for .NET provides an online [**RTF Merger App**](https://products.groupdocs.app/merger/rtf), which allows you to try it for free and check its quality and accuracy.

[!["Merge RTF"](merger/net/images/merge/merge-rtf.png)](https://products.groupdocs.app/merger/rtf)