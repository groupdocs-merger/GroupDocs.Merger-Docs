---
id: merge-ppt
url: merger/net/merge/ppt
title: Merge PPT
description: "Learn how to merge PPT files, combine PPT files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge PPT files in C#, Combine PPT files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge PPT files in C#
    appDescription: Merge PPT in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PPT files in C# 
        description: Learn how to merge PPT files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source PPT files 
          text: Create an instance of Merger class and pass source PPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other PPT files
          text: Add other PPT files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PPT files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PPT file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge PPT files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge PPT files when it's needed to organize multiple
 PPT files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine PPT documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge PPT files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source PPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PPT file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other PPT documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged PPT file as parameter.

```csharp
// Load the source PPT file
using (Merger merger = new Merger(@"c:\sample1.ppt"))
{
    // Add another PPT file to merge
    merger.Join(@"c:\sample2.ppt");
    // Merge PPT files ans save result
    merger.Save(@"c:\merged.ppt");
}
```

### About PPT File Format 

A file with PPT extension represents PowerPoint file that consists of a collection of slides for displaying as SlideShow. It specifies the Binary File Format used by Microsoft PowerPoint 97-2003. A PPT file can contain several different types of information such as text, bulleted points, images, multimedia and other embedded OLE objects. Microsoft came up with newer file format for PowerPoint, known as PPTX, from 2007 onwards that is based on Office OpenXML and is different from this binary file format.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge PPT Live Demo 

GroupDocs.Merger for .NET provides an online [**PPT Merger App**](https://products.groupdocs.app/merger/ppt), which allows you to try it for free and check its quality and accuracy.

[!["Merge PPT"](merger/net/images/merge/merge-ppt.png)](https://products.groupdocs.app/merger/ppt)