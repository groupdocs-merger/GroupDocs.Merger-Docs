---
id: how-to-merge-images-to-pdf-using-csharp
url: merger/net/getting-started/use-cases/how-to-merge-images-to-pdf-using-csharp
title: How to merge images to PDF using C#
description: "Learn how to merge images to PDF file, combine images into one PDF file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge images to PDF file in C#, Combine images to PDF file programmatically
productName: GroupDocs.Merger for .NET
weight: 9
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge images to PDF file in C#
    appDescription: Merge PDF in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge images to PDF file in C# 
        description: Learn how to merge images to PDF file in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source PDF files 
          text: Create an instance of Merger class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other image files
          text: Add other image files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PDF and image files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PDF file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## PDF Merger .NET API

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to combine multiple image documents in the preferred order and save them as a single PDF file.

## About PDF File Format

Portable Document Format (PDF) is a type of document created by Adobe back in the 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/net) to download API DLLs or MSI installer or NuGet:
```csharp
PM> Install-Package GroupDocs.Merger
```

### Source images

!["Sample1.jpg"](/merger/net/images/jpg/sample1.jpg)
!["Sample2.jpg"](/merger/net/images/jpg/sample2.jpg)
!["Sample3.jpg"](/merger/net/images/jpg/sample3.jpg)

### How to merge image files to PDF

The following example demonstrates how to merge image files to PDF file with several lines of C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. Additionally, pass instance of [LoadOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/loadoptions) class as a second constructor parameter.
* Add another image file to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged PDF file as parameter.

```csharp

// Load the source image file
using (Merger merger = new Merger(@"c:\sample1.jpeg", new LoadOptions(FileType.PDF)))
{
    // Add another image file to merge
    merger.Join(@"c:\sample2.png");
    // Add next image file to merge
    merger.Join(@"c:\sample3.bmp");
    // Merge image files and save PDF result
    merger.Save(@"c:\merged.pdf");
}
```

### Result merged PDF file

!["Merged.pdf"](/merger/net/images/jpg/merged_images_to_pdf.jpg)

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PDF Live Demo

GroupDocs.Merger for .NET provides an online [**Merge Image to PDF App**](https://products.groupdocs.app/merger/image-to-pdf), which allows you to try it for free and check its quality and accuracy.