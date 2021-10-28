---
id: merge-vstm
url: merger/net/merge/vstm
title: Merge VSTM
description: "Learn how to merge VSTM files, combine VSTM files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VSTM files in C#, Combine VSTM files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VSTM files in C#
    appDescription: Merge VSTM in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VSTM files in C# 
        description: Learn how to merge VSTM files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VSTM files 
          text: Create an instance of Merger class and pass source VSTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VSTM files
          text: Add other VSTM files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VSTM files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VSTM file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VSTM files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VSTM files when it's needed to organize multiple
 VSTM files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VSTM documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VSTM files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VSTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VSTM file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VSTM documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VSTM file as parameter.

```csharp
// Load the source VSTM file
using (Merger merger = new Merger(@"c:\sample1.vstm"))
{
    // Add another VSTM file to merge
    merger.Join(@"c:\sample2.vstm");
    // Merge VSTM files ans save result
    merger.Save(@"c:\merged.vstm");
}
```

### About VSTM File Format 

Files with VSTM extension are template files created with Microsoft Visio that support macros. Unlike VSDX files, files created from VSTM templates can run macros that are developed in Visual Basic for Applications (VBA) code. A template file can be created in order to provide basic settings of the document that can be utilized to generate further documents with these settings.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VSTM Live Demo 

GroupDocs.Merger for .NET provides an online [**VSTM Merger App**](https://products.groupdocs.app/merger/vstm), which allows you to try it for free and check its quality and accuracy.

[!["Merge VSTM"](merger/net/images/merge/merge-vstm.png)](https://products.groupdocs.app/merger/vstm)