---
id: merge-spreadsheet
url: merger/net/merge/spreadsheet
title: Merge Excel spreadsheets
linkTitle: Merge Excel
weight: 4
description: "Follow this guide and learn how to merge MS Excel spreadsheets using CSharp programming language."
keywords: Merge Excel files, Merge Spreadsheets, Merge XLS, Merge XLSX
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: True
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge XLSX files in C#
    appDescription: Merge XLSX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLSX files in C# 
        description: Learn how to merge XLSX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source XLSX files 
          text: Create an instance of Merger class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLSX files
          text: Add other XLSX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLSX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XLSX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

A **spreadsheet** file contains data in the form of rows and columns. A spreadsheet file can be saved in several different file formats, each having a different file extension for unique representation. Data is stored in cells either in plain form such as text string, numbers, date, currency, etc. or as formulas that change a cell’s value when referenced cell values change.

Common spreadsheet file extensions and their file formats include **XLSX** (Microsoft Excel Open XML Spreadsheet), **ODS** (OpenDocument Spreadsheet) and **XLS** (Microsoft Excel Binary File Format).

XLSX is well-known format for Microsoft Excel documents that was introduced by Microsoft with the release of Microsoft Office 2007. Based on structure organized according to the Open Packaging Conventions as outlined in Part 2 of the OOXML standard ECMA-376, the new format is a zip package that contains a number of XML files. The underlying structure and files can be examined by simply unzipping the .xlsx file.

## How to merge XLSX files programmatically

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge XLSX files when it's needed to organize multiple
 XLSX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XLSX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XLSX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLSX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other XLSX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged XLSX file as parameter.

```csharp
// Load the source XLSX file
using (Merger merger = new Merger(@"c:\sample1.xlsx"))
{
    // Add another XLSX file to merge
    merger.Join(@"c:\sample2.xlsx");
    // Merge XLSX files ans save result
    merger.Save(@"c:\merged.xlsx");
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLSX Live Demo

GroupDocs.Merger for .NET provides an online [**XLSX Merger App**](https://products.groupdocs.app/merger/xlsx), which allows you to try it for free and check its quality and accuracy.
