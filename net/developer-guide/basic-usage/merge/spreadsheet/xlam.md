---
id: merge-xlam
url: merger/net/merge/xlam
title: Merge XLAM
description: "Learn how to merge XLAM files, combine XLAM files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge XLAM files in C#, Combine XLAM files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge XLAM files in C#
    appDescription: Merge XLAM in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLAM files in C# 
        description: Learn how to merge XLAM files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source XLAM files 
          text: Create an instance of Merger class and pass source XLAM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLAM files
          text: Add other XLAM files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLAM files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XLAM file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge XLAM files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge XLAM files when it's needed to organize multiple
 XLAM files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XLAM documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XLAM files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source XLAM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLAM file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other XLAM documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged XLAM file as parameter.

```csharp
// Load the source XLAM file
using (Merger merger = new Merger(@"c:\sample1.xlam"))
{
    // Add another XLAM file to merge
    merger.Join(@"c:\sample2.xlam");
    // Merge XLAM files ans save result
    merger.Save(@"c:\merged.xlam");
}
```

### About XLAM File Format 

XLAM files are used to extend the modules provided by Excel. They can be added to Excel 2007 or later, or to earlier versions of Excel with Open XML component support. File used by Microsoft Excel, a program that allows users to create and edit spreadsheets; contains a macro-enabled add-in, which provides extra functionality and tools that may execute macros.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLAM Live Demo 

GroupDocs.Merger for .NET provides an online [**XLAM Merger App**](https://products.groupdocs.app/merger/xlam), which allows you to try it for free and check its quality and accuracy.

[!["Merge XLAM"](merger/net/images/merge/merge-xlam.png)](https://products.groupdocs.app/merger/xlam)