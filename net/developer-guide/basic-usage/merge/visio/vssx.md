---
id: merge-vssx
url: merger/net/merge/vssx
title: Merge VSSX
description: "Learn how to merge VSSX files, combine VSSX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VSSX files in C#, Combine VSSX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VSSX files in C#
    appDescription: Merge VSSX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VSSX files in C# 
        description: Learn how to merge VSSX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VSSX files 
          text: Create an instance of Merger class and pass source VSSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VSSX files
          text: Add other VSSX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VSSX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VSSX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VSSX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VSSX files when it's needed to organize multiple
 VSSX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VSSX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VSSX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VSSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VSSX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VSSX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VSSX file as parameter.

```csharp
// Load the source VSSX file
using (Merger merger = new Merger(@"c:\sample1.vssx"))
{
    // Add another VSSX file to merge
    merger.Join(@"c:\sample2.vssx");
    // Merge VSSX files ans save result
    merger.Save(@"c:\merged.vssx");
}
```

### About VSSX File Format 

Files with .VSSX extension are drawing stencils created with Microsoft Visio 2013 and above. The VSSX file format can be opened with Visio 2013 and above. Visio files are known for representation of a variety of drawing elements such as collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping and other similar information.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VSSX Live Demo 

GroupDocs.Merger for .NET provides an online [**VSSX Merger App**](https://products.groupdocs.app/merger/vssx), which allows you to try it for free and check its quality and accuracy.

[!["Merge VSSX"](merger/net/images/merge/merge-vssx.png)](https://products.groupdocs.app/merger/vssx)