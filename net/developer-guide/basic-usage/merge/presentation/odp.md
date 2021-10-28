---
id: merge-odp
url: merger/net/merge/odp
title: Merge ODP
description: "Learn how to merge ODP files, combine ODP files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge ODP files in C#, Combine ODP files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge ODP files in C#
    appDescription: Merge ODP in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge ODP files in C# 
        description: Learn how to merge ODP files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source ODP files 
          text: Create an instance of Merger class and pass source ODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other ODP files
          text: Add other ODP files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge ODP files and save result 
          text: Call Merger class Save method and pass the filename for the resultant ODP file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge ODP files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge ODP files when it's needed to organize multiple
 ODP files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine ODP documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge ODP files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source ODP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another ODP file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other ODP documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged ODP file as parameter.

```csharp
// Load the source ODP file
using (Merger merger = new Merger(@"c:\sample1.odp"))
{
    // Add another ODP file to merge
    merger.Join(@"c:\sample2.odp");
    // Merge ODP files ans save result
    merger.Save(@"c:\merged.odp");
}
```

### About ODP File Format 

Files with ODP extension represents the presentation file format used by OpenOffice.org in the OASIS OpenDocument standard. A presentation file is a collection of slides where each slide can comprise text, images, formatting, animations, and other media. These slides are presented to an audience in the form of slideshows with custom presentation settings.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge ODP Live Demo 

GroupDocs.Merger for .NET provides an online [**ODP Merger App**](https://products.groupdocs.app/merger/odp), which allows you to try it for free and check its quality and accuracy.

[!["Merge ODP"](merger/net/images/merge/merge-odp.png)](https://products.groupdocs.app/merger/odp)