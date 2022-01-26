---
id: merge-epub
url: merger/net/merge/epub
title: Merge EPUB
description: "Learn how to merge EPUB files, combine EPUB files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge EPUB files in C#, Combine EPUB files programmatically
productName: GroupDocs.Merger for .NET
weight: 23
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge EPUB files in C#
    appDescription: Merge EPUB in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge EPUB files in C# 
        description: Learn how to merge EPUB files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source EPUB files 
          text: Create an instance of Merger class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other EPUB files
          text: Add other EPUB files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge EPUB files and save result 
          text: Call Merger class Save method and pass the filename for the resultant EPUB file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge EPUB files in CSharp

You can easily combine multiple EPUB files into one using [GroupDocs.Merger](https://products.groupdocs.com/merger/net) library API and all the files content will be preserved.
The following example demonstrates how to merge EPUB files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another EPUB file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other EPUB documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged EPUB file as parameter.

```csharp
// Load the source EPUB file
using (Merger merger = new Merger(@"c:\sample1.epub"))
{
    // Add another EPUB file to merge
    merger.Join(@"c:\sample2.epub");
    // Merge EPUB files ans save result
    merger.Save(@"c:\merged.epub");
}
```

### About EPUB File Format 

Files with .EPUB extension are an e-book file format that provide a standard digital publication format for publishers and consumers. The format has been so common by now that it is supported by many e-readers and software applications. For example, on Mac OS, the pre-installed Books software provides the support for opening such files. In addition, there are a lot of compatible software available for smartphones, tablets and computers.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge EPUB Live Demo 

GroupDocs.Merger for .NET provides an online [**EPUB Merger App**](https://products.groupdocs.app/merger/epub), which allows you to try it for free and check its quality and accuracy.

[!["Merge EPUB"](merger/net/images/merge/merge-epub.png)](https://products.groupdocs.app/merger/epub)