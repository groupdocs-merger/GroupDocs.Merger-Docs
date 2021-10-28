---
id: merge-ods
url: merger/net/merge/ods
title: Merge ODS
description: "Learn how to merge ODS files, combine ODS files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge ODS files in C#, Combine ODS files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge ODS files in C#
    appDescription: Merge ODS in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge ODS files in C# 
        description: Learn how to merge ODS files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source ODS files 
          text: Create an instance of Merger class and pass source ODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other ODS files
          text: Add other ODS files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge ODS files and save result 
          text: Call Merger class Save method and pass the filename for the resultant ODS file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge ODS files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge ODS files when it's needed to organize multiple
 ODS files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine ODS documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge ODS files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source ODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another ODS file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other ODS documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged ODS file as parameter.

```csharp
// Load the source ODS file
using (Merger merger = new Merger(@"c:\sample1.ods"))
{
    // Add another ODS file to merge
    merger.Join(@"c:\sample2.ods");
    // Merge ODS files ans save result
    merger.Save(@"c:\merged.ods");
}
```

### About ODS File Format 

Files with ODS extension stand for OpenDocument Spreadsheet Document format that is editable by the user. Data is stored inside the ODF file into rows and columns. It is an XML-based format and is one of the several subtypes in the Open Document Formats (ODF) family. The format is specified as part of the ODF 1.2 specifications published and maintained by OASIS.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge ODS Live Demo 

GroupDocs.Merger for .NET provides an online [**ODS Merger App**](https://products.groupdocs.app/merger/ods), which allows you to try it for free and check its quality and accuracy.

[!["Merge ODS"](merger/net/images/merge/merge-ods.png)](https://products.groupdocs.app/merger/ods)