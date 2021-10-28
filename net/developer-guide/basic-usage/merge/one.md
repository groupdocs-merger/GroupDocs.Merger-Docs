---
id: merge-one
url: merger/net/merge/one
title: Merge ONE
description: "Learn how to merge ONE files, combine ONE files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge ONE files in C#, Combine ONE files programmatically
productName: GroupDocs.Merger for .NET
weight: 24
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge ONE files in C#
    appDescription: Merge ONE in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge ONE files in C# 
        description: Learn how to merge ONE files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source ONE files 
          text: Create an instance of Merger class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other ONE files
          text: Add other ONE files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge ONE files and save result 
          text: Call Merger class Save method and pass the filename for the resultant ONE file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge ONE files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge ONE files when it's needed to organize multiple
 ONE files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine ONE documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge ONE files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another ONE file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other ONE documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged ONE file as parameter.

```csharp
// Load the source ONE file
using (Merger merger = new Merger(@"c:\sample1.one"))
{
    // Add another ONE file to merge
    merger.Join(@"c:\sample2.one");
    // Merge ONE files ans save result
    merger.Save(@"c:\merged.one");
}
```

### About ONE File Format 

Files with .ONE extension are created by Microsoft OneNote application. OneNote lets you gather information using the application as if you are using your draftpad for taking notes. OneNote files can contain different elements that can be placed at non-fixed locations on document pages. These elements may contain text, digitized handwriting, and objects copied from other applications including images, drawings and multimedia (audio/video) clips.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge ONE Live Demo 

GroupDocs.Merger for .NET provides an online [**ONE Merger App**](https://products.groupdocs.app/merger/one), which allows you to try it for free and check its quality and accuracy.

[!["Merge ONE"](merger/net/images/merge/merge-one.png)](https://products.groupdocs.app/merger/one)