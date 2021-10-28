---
id: merge-tsv
url: merger/net/merge/tsv
title: Merge TSV
description: "Learn how to merge TSV files, combine TSV files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge TSV files in C#, Combine TSV files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge TSV files in C#
    appDescription: Merge TSV in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge TSV files in C# 
        description: Learn how to merge TSV files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source TSV files 
          text: Create an instance of Merger class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other TSV files
          text: Add other TSV files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge TSV files and save result 
          text: Call Merger class Save method and pass the filename for the resultant TSV file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge TSV files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge TSV files when it's needed to organize multiple
 TSV files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine TSV documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge TSV files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another TSV file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other TSV documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged TSV file as parameter.

```csharp
// Load the source TSV file
using (Merger merger = new Merger(@"c:\sample1.tsv"))
{
    // Add another TSV file to merge
    merger.Join(@"c:\sample2.tsv");
    // Merge TSV files ans save result
    merger.Save(@"c:\merged.tsv");
}
```

### About TSV File Format 

A Tab-Separated Values (TSV) file format represents data separated with tabs in plain text format. The file format, similar to CSV, is used for organization of data in a structured manner in order to import and export between different applications. The format is primarily used for data import/export and exchange in Spreadsheet applications and databases. 

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge TSV Live Demo 

GroupDocs.Merger for .NET provides an online [**TSV Merger App**](https://products.groupdocs.app/merger/tsv), which allows you to try it for free and check its quality and accuracy.

[!["Merge TSV"](merger/net/images/merge/merge-tsv.png)](https://products.groupdocs.app/merger/tsv)