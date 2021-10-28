---
id: merge-pps
url: merger/net/merge/pps
title: Merge PPS
description: "Learn how to merge PPS files, combine PPS files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge PPS files in C#, Combine PPS files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge PPS files in C#
    appDescription: Merge PPS in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PPS files in C# 
        description: Learn how to merge PPS files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source PPS files 
          text: Create an instance of Merger class and pass source PPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other PPS files
          text: Add other PPS files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PPS files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PPS file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge PPS files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge PPS files when it's needed to organize multiple
 PPS files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine PPS documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge PPS files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source PPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PPS file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other PPS documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged PPS file as parameter.

```csharp
// Load the source PPS file
using (Merger merger = new Merger(@"c:\sample1.pps"))
{
    // Add another PPS file to merge
    merger.Join(@"c:\sample2.pps");
    // Merge PPS files ans save result
    merger.Save(@"c:\merged.pps");
}
```

### About PPS File Format 

PPS, PowerPoint Slide Show, files are created using Microsoft PowerPoint for Slide Show purpose. PPS file reading and creation is supported by Microsoft PowerPoint 97-2003. The more latest version of this file format is PPSX which is based on Office OpenXML standards. PPS files can still be read by latest versions of Microsoft PowerPoint, but newly created files can only be saved in PPSX file format. When a PPS file is shared with another user and opened, it starts as Powerpoint show unlike PPT file which opens in editable mode. 

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge PPS Live Demo 

GroupDocs.Merger for .NET provides an online [**PPS Merger App**](https://products.groupdocs.app/merger/pps), which allows you to try it for free and check its quality and accuracy.

[!["Merge PPS"](merger/net/images/merge/merge-pps.png)](https://products.groupdocs.app/merger/pps)