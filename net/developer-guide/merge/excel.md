---
id: merge-excel
url: merger/net/merge/excel
title: Merge Excel spreadsheets
linkTitle: Merge Excel
weight: 60
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

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLSX file to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method. Repeat this step for other XLSX documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged XLSX file as parameter.

```csharp
// Load the source XLSX file
using (Merger merger = new Merger(@"c:\sample1.xlsx"))
{
    // Add another XLSX file to merge
    merger.Join(@"c:\sample2.xlsx");
    // Merge XLSX files and save result
    merger.Save(@"c:\merged.xlsx");
}
```

## How to merge rows of several spreadsheets into a single sheet

By default, each joined spreadsheet is added to the result as separate worksheets. To append the rows of the joined spreadsheets below the existing data instead — for example, to collect monthly reports into one table — use [SpreadsheetJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/spreadsheetjoinoptions/) with [SpreadsheetJoinMode](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/spreadsheetjoinmode/)`.Rows`:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass the first spreadsheet file path as a constructor parameter. This document is always taken in full.
* Create an instance of [SpreadsheetJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/spreadsheetjoinoptions/) class, set `Mode` to `SpreadsheetJoinMode.Rows` and, if the joined files have header rows, set `SkipRows` to the number of rows to skip.
* Add the other spreadsheets with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method and pass the options as a parameter. The rows of each file are appended below the last row containing data of the matching worksheet.
* Call [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged spreadsheet.

The following code sample demonstrates how to merge rows of several spreadsheets into a single sheet:

```csharp
// Load the first spreadsheet
using (Merger merger = new Merger(@"c:\january.xlsx"))
{
    // Append rows instead of adding worksheets, and skip the header row of each joined file
    SpreadsheetJoinOptions joinOptions = new SpreadsheetJoinOptions
    {
        Mode = SpreadsheetJoinMode.Rows,
        SkipRows = 1
    };
    merger.Join(@"c:\february.xlsx", joinOptions);
    merger.Join(@"c:\march.xlsx", joinOptions);
    // Save the merged spreadsheet
    merger.Save(@"c:\q1.xlsx");
}
```

### Matching worksheets

When the spreadsheets have several worksheets, [SpreadsheetSheetMatching](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/spreadsheetsheetmatching/) set through the `SheetMatching` property controls where the rows go:

* `ByIndex` (default) — the rows of the n-th worksheet of a joined file are appended to the n-th worksheet of the result. Worksheets beyond the number of result worksheets are added as new worksheets.
* `FirstSheetOnly` — only the first worksheet of each joined file is appended, to the first worksheet of the result.

`SkipRows` and `SheetMatching` have no effect when `Mode` is `SpreadsheetJoinMode.Worksheets`.

### What is carried over

Row-wise joining carries cell values, formulas (relative references are adjusted to the new position), cell styles, merged cells and row heights. Charts, pictures and other floating objects, pivot tables, tables, conditional formatting and data validation of the joined files are not carried over.

Row-wise joining works for XLSX, XLS, XLSM, XLSB, XLTX, XLTM, XLT, XLAM and ODS, also when a joined spreadsheet has a different format than the first one (for example, XLS joined into XLSX).

{{< alert style="warning" >}}
* A negative `SkipRows` value throws `GroupDocsMergerException`.
* Appending more rows than the output format allows (65,536 rows for XLS and XLT, 1,048,576 rows for the other formats) throws `GroupDocsMergerException`.
* [ApplyPageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/applypagebuilder) throws `GroupDocsMergerException` while a spreadsheet joined in `Rows` mode is pending, because appended rows do not form separate pages.
{{< /alert >}}

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLSX Live Demo

GroupDocs.Merger for .NET provides an online [**XLSX Merger App**](https://products.groupdocs.app/merger/xlsx), which allows you to try it for free and check its quality and accuracy.
