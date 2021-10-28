---
id: merge-ppsx
url: merger/net/merge/ppsx
title: Merge PPSX
description: "Learn how to merge PPSX files, combine PPSX files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge PPSX files in C#, Combine PPSX files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge PPSX files in C#
    appDescription: Merge PPSX in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PPSX files in C# 
        description: Learn how to merge PPSX files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source PPSX files 
          text: Create an instance of Merger class and pass source PPSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other PPSX files
          text: Add other PPSX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PPSX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PPSX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge PPSX files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge PPSX files when it's needed to organize multiple
 PPSX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine PPSX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge PPSX files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source PPSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PPSX file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other PPSX documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged PPSX file as parameter.

```csharp
// Load the source PPSX file
using (Merger merger = new Merger(@"c:\sample1.ppsx"))
{
    // Add another PPSX file to merge
    merger.Join(@"c:\sample2.ppsx");
    // Merge PPSX files ans save result
    merger.Save(@"c:\merged.ppsx");
}
```

### About PPSX File Format 

PPSX, Power Point Slide Show, file are created using Microsoft PowerPoint 2007 and above for Slide Show purpose. It is an update to the PPS file format that was supported by Microsoft PowerPoint 97-2003 versions. When a PPSX file is shared with another user and opened, it starts as PowerPoint show unlike PPTX file that opens in editable mode. The sequence of slide show is the same as in the original presentation. All the slides accompany the images, sounds and other embedded media accompany the presentation slides to the PPSX during the slideshow. 

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge PPSX Live Demo 

GroupDocs.Merger for .NET provides an online [**PPSX Merger App**](https://products.groupdocs.app/merger/ppsx), which allows you to try it for free and check its quality and accuracy.

[!["Merge PPSX"](merger/net/images/merge/merge-ppsx.png)](https://products.groupdocs.app/merger/ppsx)