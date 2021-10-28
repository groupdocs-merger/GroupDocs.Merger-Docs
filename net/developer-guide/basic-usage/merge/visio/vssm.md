---
id: merge-vssm
url: merger/net/merge/vssm
title: Merge VSSM
description: "Learn how to merge VSSM files, combine VSSM files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VSSM files in C#, Combine VSSM files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VSSM files in C#
    appDescription: Merge VSSM in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VSSM files in C# 
        description: Learn how to merge VSSM files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VSSM files 
          text: Create an instance of Merger class and pass source VSSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VSSM files
          text: Add other VSSM files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VSSM files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VSSM file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VSSM files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VSSM files when it's needed to organize multiple
 VSSM files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VSSM documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VSSM files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VSSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VSSM file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VSSM documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VSSM file as parameter.

```csharp
// Load the source VSSM file
using (Merger merger = new Merger(@"c:\sample1.vssm"))
{
    // Add another VSSM file to merge
    merger.Join(@"c:\sample2.vssm");
    // Merge VSSM files ans save result
    merger.Save(@"c:\merged.vssm");
}
```

### About VSSM File Format 

Files with .VSSM extension are Microsoft Visio Stencil files that support provide support for macros. A VSSM file when opened allows running the macros to achieve the desired formatting and placement of shapes in a diagram. In general, Microsoft Visio is drawing software that allows creating files that can contain and represent user-defined information in different shapes.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VSSM Live Demo 

GroupDocs.Merger for .NET provides an online [**VSSM Merger App**](https://products.groupdocs.app/merger/vssm), which allows you to try it for free and check its quality and accuracy.

[!["Merge VSSM"](merger/net/images/merge/merge-vssm.png)](https://products.groupdocs.app/merger/vssm)