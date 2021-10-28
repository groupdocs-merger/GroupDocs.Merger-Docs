---
id: merge-xlt
url: merger/net/merge/xlt
title: Merge XLT
description: "Learn how to merge XLT files, combine XLT files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge XLT files in C#, Combine XLT files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge XLT files in C#
    appDescription: Merge XLT in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLT files in C# 
        description: Learn how to merge XLT files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source XLT files 
          text: Create an instance of Merger class and pass source XLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLT files
          text: Add other XLT files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLT files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XLT file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge XLT files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge XLT files when it's needed to organize multiple
 XLT files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XLT documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XLT files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source XLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLT file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other XLT documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged XLT file as parameter.

```csharp
// Load the source XLT file
using (Merger merger = new Merger(@"c:\sample1.xlt"))
{
    // Add another XLT file to merge
    merger.Join(@"c:\sample2.xlt");
    // Merge XLT files ans save result
    merger.Save(@"c:\merged.xlt");
}
```

### About XLT File Format 

Files with .XLT extension are template files created with Microsoft Excel which is a spreadsheet application which comes as part of Microsoft Office suite. Microsoft Office 97-2003 supported creating new XLT files as well as opening these. The latest version of Excel is still capable of opening these old format template files. Such a template file is used to quickly create new Excel files with default data and settings such as page formatting, font size, margins, charts, etc which can be further saved as new .XLS files.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLT Live Demo 

GroupDocs.Merger for .NET provides an online [**XLT Merger App**](https://products.groupdocs.app/merger/xlt), which allows you to try it for free and check its quality and accuracy.

[!["Merge XLT"](merger/net/images/merge/merge-xlt.png)](https://products.groupdocs.app/merger/xlt)