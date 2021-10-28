---
id: merge-docm
url: merger/net/merge/docm
title: Merge DOCM
description: "Learn how to merge DOCM files, combine DOCM files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge DOCM files in C#, Combine DOCM files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge DOCM files in C#
    appDescription: Merge DOCM in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge DOCM files in C# 
        description: Learn how to merge DOCM files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source DOCM files 
          text: Create an instance of Merger class and pass source DOCM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other DOCM files
          text: Add other DOCM files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge DOCM files and save result 
          text: Call Merger class Save method and pass the filename for the resultant DOCM file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge DOCM files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge DOCM files when it's needed to organize multiple
 DOCM files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine DOCM documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge DOCM files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source DOCM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another DOCM file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other DOCM documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged DOCM file as parameter.

```csharp
// Load the source DOCM file
using (Merger merger = new Merger(@"c:\sample1.docm"))
{
    // Add another DOCM file to merge
    merger.Join(@"c:\sample2.docm");
    // Merge DOCM files ans save result
    merger.Save(@"c:\merged.docm");
}
```

### About DOCM File Format 

DOCM files are Microsoft Word 2007 or higher generated documents with the ability to run macros. It is similar to DOCX file format but the ability to run macros makes it different from DOCX. Like DOCX, DOCM files can be store text, images, tables, shapes, charts and other contents. The capability to run macros make it easy to save time by executing the series of commands in the form of recorded actions for automatic completion of a task. DOCM files can be opened and edited in Microsoft Word 2007 and above.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge DOCM Live Demo 

GroupDocs.Merger for .NET provides an online [**DOCM Merger App**](https://products.groupdocs.app/merger/docm), which allows you to try it for free and check its quality and accuracy.

[!["Merge DOCM"](merger/net/images/merge/merge-docm.png)](https://products.groupdocs.app/merger/docm)