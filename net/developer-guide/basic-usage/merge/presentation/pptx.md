---
id: merge-pptx
url: merger/net/merge/pptx
title: Merge PPTX
description: "Learn how to merge PPTX files, combine PPTX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge PPTX files in C#, Combine PPTX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge PPTX files in C#
    appDescription: Merge PPTX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PPTX files in C# 
        description: Learn how to merge PPTX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source PPTX files 
          text: Create an instance of Merger class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other PPTX files
          text: Add other PPTX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PPTX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PPTX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge PPTX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge PPTX files when it's needed to organize multiple
 PPTX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine PPTX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge PPTX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PPTX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other PPTX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged PPTX file as parameter.

```csharp
// Load the source PPTX file
using (Merger merger = new Merger(@"c:\sample1.pptx"))
{
    // Add another PPTX file to merge
    merger.Join(@"c:\sample2.pptx");
    // Merge PPTX files ans save result
    merger.Save(@"c:\merged.pptx");
}
```

### About PPTX File Format 

Files with PPTX extension are presentation files created with popular Microsoft PowerPoint application. Unlike the previous version of presentation file format PPT which was binary, the PPTX format is based on the Microsoft PowerPoint open XML presentation file format. A presentation file is a collection of slides where each slide can comprise of text, images, formatting, animations, and other media.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge PPTX Live Demo 

GroupDocs.Merger for .NET provides an online [**PPTX Merger App**](https://products.groupdocs.app/merger/pptx), which allows you to try it for free and check its quality and accuracy.

[!["Merge PPTX"](merger/net/images/merge/merge-pptx.png)](https://products.groupdocs.app/merger/pptx)