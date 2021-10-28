---
id: merge-mhtml
url: merger/net/merge/mhtml
title: Merge MHTML
description: "Learn how to merge MHTML files, combine MHTML files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge MHTML files in C#, Combine MHTML files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge MHTML files in C#
    appDescription: Merge MHTML in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge MHTML files in C# 
        description: Learn how to merge MHTML files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source MHTML files 
          text: Create an instance of Merger class and pass source MHTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other MHTML files
          text: Add other MHTML files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge MHTML files and save result 
          text: Call Merger class Save method and pass the filename for the resultant MHTML file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge MHTML files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge MHTML files when it's needed to organize multiple
 MHTML files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine MHTML documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge MHTML files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source MHTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another MHTML file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other MHTML documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged MHTML file as parameter.

```csharp
// Load the source MHTML file
using (Merger merger = new Merger(@"c:\sample1.mhtml"))
{
    // Add another MHTML file to merge
    merger.Join(@"c:\sample2.mhtml");
    // Merge MHTML files ans save result
    merger.Save(@"c:\merged.mhtml");
}
```

### About MHTML File Format 

Files with MHTML extension represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge MHTML Live Demo 

GroupDocs.Merger for .NET provides an online [**MHTML Merger App**](https://products.groupdocs.app/merger/mhtml), which allows you to try it for free and check its quality and accuracy.

[!["Merge MHTML"](merger/net/images/merge/merge-mhtml.png)](https://products.groupdocs.app/merger/mhtml)