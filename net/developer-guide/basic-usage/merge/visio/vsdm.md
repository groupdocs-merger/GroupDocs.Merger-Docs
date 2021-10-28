---
id: merge-vsdm
url: merger/net/merge/vsdm
title: Merge VSDM
description: "Learn how to merge VSDM files, combine VSDM files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VSDM files in C#, Combine VSDM files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VSDM files in C#
    appDescription: Merge VSDM in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VSDM files in C# 
        description: Learn how to merge VSDM files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VSDM files 
          text: Create an instance of Merger class and pass source VSDM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VSDM files
          text: Add other VSDM files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VSDM files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VSDM file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VSDM files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VSDM files when it's needed to organize multiple
 VSDM files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VSDM documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VSDM files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VSDM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VSDM file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VSDM documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VSDM file as parameter.

```csharp
// Load the source VSDM file
using (Merger merger = new Merger(@"c:\sample1.vsdm"))
{
    // Add another VSDM file to merge
    merger.Join(@"c:\sample2.vsdm");
    // Merge VSDM files ans save result
    merger.Save(@"c:\merged.vsdm");
}
```

### About VSDM File Format 

Files with VSDM extension are drawing files created with Microsoft Visio application that supports macros. VSDM files are OPC/XML drawings that are similar to VSDX but also provide the capability to run macros when the file is opened. Macros are user-defined actions/steps that are developed in Visual Basic for Applications (VBA) and can be used to perform repetitive tasks.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VSDM Live Demo 

GroupDocs.Merger for .NET provides an online [**VSDM Merger App**](https://products.groupdocs.app/merger/vsdm), which allows you to try it for free and check its quality and accuracy.

[!["Merge VSDM"](merger/net/images/merge/merge-vsdm.png)](https://products.groupdocs.app/merger/vsdm)