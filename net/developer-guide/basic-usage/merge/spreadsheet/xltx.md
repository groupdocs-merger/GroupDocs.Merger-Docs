---
id: merge-xltx
url: merger/net/merge/xltx
title: Merge XLTX
description: "Learn how to merge XLTX files, combine XLTX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge XLTX files in C#, Combine XLTX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge XLTX files in C#
    appDescription: Merge XLTX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLTX files in C# 
        description: Learn how to merge XLTX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source XLTX files 
          text: Create an instance of Merger class and pass source XLTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLTX files
          text: Add other XLTX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLTX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XLTX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge XLTX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge XLTX files when it's needed to organize multiple
 XLTX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XLTX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XLTX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source XLTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLTX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other XLTX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged XLTX file as parameter.

```csharp
// Load the source XLTX file
using (Merger merger = new Merger(@"c:\sample1.xltx"))
{
    // Add another XLTX file to merge
    merger.Join(@"c:\sample2.xltx");
    // Merge XLTX files ans save result
    merger.Save(@"c:\merged.xltx");
}
```

### About XLTX File Format 

Files with XLTX extension represent Microsoft Excel Template files that are based on the Office OpenXML file format specifications. It is used to create a standard template file that can be utilized to generate XLSX files that exhibit the same settings as specified in the XLTX file.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLTX Live Demo 

GroupDocs.Merger for .NET provides an online [**XLTX Merger App**](https://products.groupdocs.app/merger/xltx), which allows you to try it for free and check its quality and accuracy.

[!["Merge XLTX"](merger/net/images/merge/merge-xltx.png)](https://products.groupdocs.app/merger/xltx)