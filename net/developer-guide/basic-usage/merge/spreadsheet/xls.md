---
id: merge-xls
url: merger/net/merge/xls
title: Merge XLS
description: "Learn how to merge XLS files, combine XLS files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge XLS files in C#, Combine XLS files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge XLS files in C#
    appDescription: Merge XLS in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLS files in C# 
        description: Learn how to merge XLS files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source XLS files 
          text: Create an instance of Merger class and pass source XLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLS files
          text: Add other XLS files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLS files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XLS file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge XLS files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge XLS files when it's needed to organize multiple
 XLS files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XLS documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XLS files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source XLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLS file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other XLS documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged XLS file as parameter.

```csharp
// Load the source XLS file
using (Merger merger = new Merger(@"c:\sample1.xls"))
{
    // Add another XLS file to merge
    merger.Join(@"c:\sample2.xls");
    // Merge XLS files ans save result
    merger.Save(@"c:\merged.xls");
}
```

### About XLS File Format 

Files with XLS extension represent Excel Binary File Format. Such files can be created by Microsoft Excel as well as other similar spreadsheet programs such as OpenOffice Calc or Apple Numbers. File saved by Excel are known as Workbook where each workbook can have one or more worksheets. Data is stored and displayed to users in table format in worksheet and can span numeric values, text data, formulas, external data connections, images and charts.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLS Live Demo 

GroupDocs.Merger for .NET provides an online [**XLS Merger App**](https://products.groupdocs.app/merger/xls), which allows you to try it for free and check its quality and accuracy.

[!["Merge XLS"](merger/net/images/merge/merge-xls.png)](https://products.groupdocs.app/merger/xls)