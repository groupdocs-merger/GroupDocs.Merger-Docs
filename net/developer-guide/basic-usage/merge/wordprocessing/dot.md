---
id: merge-dot
url: merger/net/merge/dot
title: Merge DOT
description: "Learn how to merge DOT files, combine DOT files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge DOT files in C#, Combine DOT files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge DOT files in C#
    appDescription: Merge DOT in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge DOT files in C# 
        description: Learn how to merge DOT files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source DOT files 
          text: Create an instance of Merger class and pass source DOT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other DOT files
          text: Add other DOT files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge DOT files and save result 
          text: Call Merger class Save method and pass the filename for the resultant DOT file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge DOT files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge DOT files when it's needed to organize multiple
 DOT files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine DOT documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge DOT files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source DOT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another DOT file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other DOT documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged DOT file as parameter.

```csharp
// Load the source DOT file
using (Merger merger = new Merger(@"c:\sample1.dot"))
{
    // Add another DOT file to merge
    merger.Join(@"c:\sample2.dot");
    // Merge DOT files ans save result
    merger.Save(@"c:\merged.dot");
}
```

### About DOT File Format 

Files with .DOT extension are template files created by Microsoft Word to have pre-formatted settings for generation of further DOC or DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from these. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge DOT Live Demo 

GroupDocs.Merger for .NET provides an online [**DOT Merger App**](https://products.groupdocs.app/merger/dot), which allows you to try it for free and check its quality and accuracy.

[!["Merge DOT"](merger/net/images/merge/merge-dot.png)](https://products.groupdocs.app/merger/dot)