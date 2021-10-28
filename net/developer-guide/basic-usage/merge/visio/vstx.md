---
id: merge-vstx
url: merger/net/merge/vstx
title: Merge VSTX
description: "Learn how to merge VSTX files, combine VSTX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VSTX files in C#, Combine VSTX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VSTX files in C#
    appDescription: Merge VSTX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VSTX files in C# 
        description: Learn how to merge VSTX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VSTX files 
          text: Create an instance of Merger class and pass source VSTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VSTX files
          text: Add other VSTX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VSTX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VSTX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VSTX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VSTX files when it's needed to organize multiple
 VSTX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VSTX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VSTX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VSTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VSTX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VSTX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VSTX file as parameter.

```csharp
// Load the source VSTX file
using (Merger merger = new Merger(@"c:\sample1.vstx"))
{
    // Add another VSTX file to merge
    merger.Join(@"c:\sample2.vstx");
    // Merge VSTX files ans save result
    merger.Save(@"c:\merged.vstx");
}
```

### About VSTX File Format 

Files with VSTX extensions are drawing template files created with Microsoft Visio 2013 and above. These VSTX files provide a starting point for creating Visio drawings, saved as VSDX files, with default layout and settings. In general, Visio files are used to create drawings that contain visual objects, flow charts, UML diagrams, information flow, organizational charts, software diagrams, network layout, database models, objects mapping, and other similar information.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VSTX Live Demo 

GroupDocs.Merger for .NET provides an online [**VSTX Merger App**](https://products.groupdocs.app/merger/vstx), which allows you to try it for free and check its quality and accuracy.

[!["Merge VSTX"](merger/net/images/merge/merge-vstx.png)](https://products.groupdocs.app/merger/vstx)