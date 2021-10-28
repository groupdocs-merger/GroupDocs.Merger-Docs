---
id: merge-dotm
url: merger/net/merge/dotm
title: Merge DOTM
description: "Learn how to merge DOTM files, combine DOTM files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge DOTM files in C#, Combine DOTM files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge DOTM files in C#
    appDescription: Merge DOTM in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge DOTM files in C# 
        description: Learn how to merge DOTM files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source DOTM files 
          text: Create an instance of Merger class and pass source DOTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other DOTM files
          text: Add other DOTM files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge DOTM files and save result 
          text: Call Merger class Save method and pass the filename for the resultant DOTM file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge DOTM files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge DOTM files when it's needed to organize multiple
 DOTM files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine DOTM documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge DOTM files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source DOTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another DOTM file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other DOTM documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged DOTM file as parameter.

```csharp
// Load the source DOTM file
using (Merger merger = new Merger(@"c:\sample1.dotm"))
{
    // Add another DOTM file to merge
    merger.Join(@"c:\sample2.dotm");
    // Merge DOTM files ans save result
    merger.Save(@"c:\merged.dotm");
}
```

### About DOTM File Format 

A file with DOTM extension represents template file created with Microsoft Word 2007 or higher. It is similar to the popular DOCX file format other than it retains the user defined settings for reuse in case of creating new documents. Such documents are more often used in offices where a standard template file is generated with settings like page information, margins, default layout and macros, and is used to create new documents from it when required. DOTM files, however, save macros, that are a series of commands in the form of recorded actions for automatic completion of a task. This helps save time in carrying out actions that are repeated in completion of a task.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge DOTM Live Demo 

GroupDocs.Merger for .NET provides an online [**DOTM Merger App**](https://products.groupdocs.app/merger/dotm), which allows you to try it for free and check its quality and accuracy.

[!["Merge DOTM"](merger/net/images/merge/merge-dotm.png)](https://products.groupdocs.app/merger/dotm)