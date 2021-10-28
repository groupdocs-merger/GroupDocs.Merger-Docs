---
id: merge-vsdx
url: merger/net/merge/vsdx
title: Merge VSDX
description: "Learn how to merge VSDX files, combine VSDX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VSDX files in C#, Combine VSDX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VSDX files in C#
    appDescription: Merge VSDX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VSDX files in C# 
        description: Learn how to merge VSDX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VSDX files 
          text: Create an instance of Merger class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VSDX files
          text: Add other VSDX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VSDX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VSDX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VSDX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VSDX files when it's needed to organize multiple
 VSDX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VSDX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VSDX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VSDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VSDX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VSDX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VSDX file as parameter.

```csharp
// Load the source VSDX file
using (Merger merger = new Merger(@"c:\sample1.vsdx"))
{
    // Add another VSDX file to merge
    merger.Join(@"c:\sample2.vsdx");
    // Merge VSDX files ans save result
    merger.Save(@"c:\merged.vsdx");
}
```

### About VSDX File Format 

Files with .VSDX extension represents Microsoft Visio file format introduced from Microsoft Office 2013 onwards. It was developed to replace the binary file format, .VSD, which is supported by earlier versions of Microsoft Visio. It is also supported on Visio Services in Microsoft SharePoint Server 2013 and does not require an intermediary file format for publishing to SharePoint Server.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VSDX Live Demo 

GroupDocs.Merger for .NET provides an online [**VSDX Merger App**](https://products.groupdocs.app/merger/vsdx), which allows you to try it for free and check its quality and accuracy.

[!["Merge VSDX"](merger/net/images/merge/merge-vsdx.png)](https://products.groupdocs.app/merger/vsdx)