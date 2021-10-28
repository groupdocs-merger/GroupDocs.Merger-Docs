---
id: merge-xps
url: merger/net/merge/xps
title: Merge XPS
description: "Learn how to merge XPS files, combine XPS files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge XPS files in C#, Combine XPS files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge XPS files in C#
    appDescription: Merge XPS in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XPS files in C# 
        description: Learn how to merge XPS files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source XPS files 
          text: Create an instance of Merger class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XPS files
          text: Add other XPS files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XPS files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XPS file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge XPS files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge XPS files when it's needed to organize multiple
 XPS files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XPS documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XPS files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source XPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XPS file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other XPS documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged XPS file as parameter.

```csharp
// Load the source XPS file
using (Merger merger = new Merger(@"c:\sample1.xps"))
{
    // Add another XPS file to merge
    merger.Join(@"c:\sample2.xps");
    // Merge XPS files ans save result
    merger.Save(@"c:\merged.xps");
}
```

### About XPS File Format 

An XPS file represents page layout files that are based on XML Paper Specifications created by Microsoft. This format was developed by Microsoft as replacement of EMF file format and is similar to PDF file format, but uses XML in layout, appearance, and printing information of a document. It is, in fact, more justified to say that XPS is an attempt on PDF, but couldn't get enough popularity as owned by PDF for a number of reasons.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge XPS Live Demo 

GroupDocs.Merger for .NET provides an online [**XPS Merger App**](https://products.groupdocs.app/merger/xps), which allows you to try it for free and check its quality and accuracy.

[!["Merge XPS"](merger/net/images/merge/merge-xps.png)](https://products.groupdocs.app/merger/xps)