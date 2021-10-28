---
id: merge-vtx
url: merger/net/merge/vtx
title: Merge VTX
description: "Learn how to merge VTX files, combine VTX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VTX files in C#, Combine VTX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VTX files in C#
    appDescription: Merge VTX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VTX files in C# 
        description: Learn how to merge VTX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VTX files 
          text: Create an instance of Merger class and pass source VTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VTX files
          text: Add other VTX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VTX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VTX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VTX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VTX files when it's needed to organize multiple
 VTX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VTX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VTX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VTX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VTX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VTX file as parameter.

```csharp
// Load the source VTX file
using (Merger merger = new Merger(@"c:\sample1.vtx"))
{
    // Add another VTX file to merge
    merger.Join(@"c:\sample2.vtx");
    // Merge VTX files ans save result
    merger.Save(@"c:\merged.vtx");
}
```

### About VTX File Format 

A file with VTX extension is a Microsoft Visio drawing template that is saved to disc in XML file format. The template is aimed to provide a file with basic settings that can be used to create multiple Visio files of the same settings. Another similar format is VST which is saved in binary format rather than XML. VTX files are supported with Visio 2010 and newer versions.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VTX Live Demo 

GroupDocs.Merger for .NET provides an online [**VTX Merger App**](https://products.groupdocs.app/merger/vtx), which allows you to try it for free and check its quality and accuracy.

[!["Merge VTX"](merger/net/images/merge/merge-vtx.png)](https://products.groupdocs.app/merger/vtx)