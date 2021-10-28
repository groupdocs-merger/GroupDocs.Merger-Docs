---
id: merge-vdx
url: merger/net/merge/vdx
title: Merge VDX
description: "Learn how to merge VDX files, combine VDX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VDX files in C#, Combine VDX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VDX files in C#
    appDescription: Merge VDX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VDX files in C# 
        description: Learn how to merge VDX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VDX files 
          text: Create an instance of Merger class and pass source VDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VDX files
          text: Add other VDX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VDX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VDX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VDX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VDX files when it's needed to organize multiple
 VDX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VDX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VDX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VDX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VDX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VDX file as parameter.

```csharp
// Load the source VDX file
using (Merger merger = new Merger(@"c:\sample1.vdx"))
{
    // Add another VDX file to merge
    merger.Join(@"c:\sample2.vdx");
    // Merge VDX files ans save result
    merger.Save(@"c:\merged.vdx");
}
```

### About VDX File Format 

Any drawing or chart created in Microsoft Visio, but saved in XML format has a VDX extension. A Visio drawing XML file is created in Visio software, which is developed by Microsoft. Microsoft Visio has the capability to generate visual documents that can be used in presentations and documents. The Visio drawing XML file contains the visual objects and metadata details of the visual elements.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VDX Live Demo 

GroupDocs.Merger for .NET provides an online [**VDX Merger App**](https://products.groupdocs.app/merger/vdx), which allows you to try it for free and check its quality and accuracy.

[!["Merge VDX"](merger/net/images/merge/merge-vdx.png)](https://products.groupdocs.app/merger/vdx)