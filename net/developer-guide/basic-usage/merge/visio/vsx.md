---
id: merge-vsx
url: merger/net/merge/vsx
title: Merge VSX
description: "Learn how to merge VSX files, combine VSX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge VSX files in C#, Combine VSX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge VSX files in C#
    appDescription: Merge VSX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge VSX files in C# 
        description: Learn how to merge VSX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source VSX files 
          text: Create an instance of Merger class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other VSX files
          text: Add other VSX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge VSX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant VSX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge VSX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge VSX files when it's needed to organize multiple
 VSX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine VSX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge VSX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another VSX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other VSX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged VSX file as parameter.

```csharp
// Load the source VSX file
using (Merger merger = new Merger(@"c:\sample1.vsx"))
{
    // Add another VSX file to merge
    merger.Join(@"c:\sample2.vsx");
    // Merge VSX files ans save result
    merger.Save(@"c:\merged.vsx");
}
```

### About VSX File Format 

Files with .VSX extension refer to stencils that consist of drawings and shapes that are used for creating diagrams in Microsoft Visio. VSX files are saved in XML file format and was supported till Visio 2013. These are different than the primary VSDX file format that was introduced with Microsoft Visio 2013. VSX files can be opened in any text editor to view the contents.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge VSX Live Demo 

GroupDocs.Merger for .NET provides an online [**VSX Merger App**](https://products.groupdocs.app/merger/vsx), which allows you to try it for free and check its quality and accuracy.

[!["Merge VSX"](merger/net/images/merge/merge-vsx.png)](https://products.groupdocs.app/merger/vsx)