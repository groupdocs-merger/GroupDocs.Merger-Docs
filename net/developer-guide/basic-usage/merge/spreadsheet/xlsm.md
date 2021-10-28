---
id: merge-xlsm
url: merger/net/merge/xlsm
title: Merge XLSM
description: "Learn how to merge XLSM files, combine XLSM files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge XLSM files in C#, Combine XLSM files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge XLSM files in C#
    appDescription: Merge XLSM in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLSM files in C# 
        description: Learn how to merge XLSM files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source XLSM files 
          text: Create an instance of Merger class and pass source XLSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLSM files
          text: Add other XLSM files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLSM files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XLSM file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge XLSM files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge XLSM files when it's needed to organize multiple
 XLSM files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XLSM documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XLSM files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source XLSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLSM file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other XLSM documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged XLSM file as parameter.

```csharp
// Load the source XLSM file
using (Merger merger = new Merger(@"c:\sample1.xlsm"))
{
    // Add another XLSM file to merge
    merger.Join(@"c:\sample2.xlsm");
    // Merge XLSM files ans save result
    merger.Save(@"c:\merged.xlsm");
}
```

### About XLSM File Format 

Files with XLSM extension is a type of Spreasheet files that support Macros. From application point of view, a Macro is set of instructions that are used for automating processes. A macro is used to record the steps that are performed repeatedly and facilitates performing the actions by running the macro again. Macros are programmed with Microsoft's Visual Basic for Applications (VBA) from within the Excel Workbook using the Visual Basic Editor and can be run/debug directly from there.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLSM Live Demo 

GroupDocs.Merger for .NET provides an online [**XLSM Merger App**](https://products.groupdocs.app/merger/xlsm), which allows you to try it for free and check its quality and accuracy.

[!["Merge XLSM"](merger/net/images/merge/merge-xlsm.png)](https://products.groupdocs.app/merger/xlsm)