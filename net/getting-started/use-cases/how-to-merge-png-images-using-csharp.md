---
id: how-to-merge-png-images-using-csharp
url: merger/net/getting-started/use-cases/how-to-merge-png-images-using-csharp
title: How to merge PNG images using C#
description: "Learn how to merge PNG image files, combine PNG image files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge PNG image files in C#, Combine PNG image files programmatically
productName: GroupDocs.Merger for .NET
weight: 2
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge PNG image files in C#
    appDescription: Merge PNG image in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PNG image files in C# 
        description: Learn how to merge PNG image files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source image files 
          text: Create an instance of Merger class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other image files
          text: Add other image files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge image files and save result 
          text: Call Merger class Save method and pass the filename for the resultant image file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## PNG Merger .NET API

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to combine multiple PNG documents in the preferred order and save them as a single file.

## About PNG File Format

PNG, Portable Network Graphics, refers to a type of raster image file format that use loseless compression. This file format was created as a replacement of Graphics Interchange Format (GIF) and has no copyright limitations. However, PNG file format does not support animations. PNG file format supports loseless image compression that makes it popular among its users. With the passage of time, PNG has evolved as one of the mostly used image file format.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/net) to download API DLLs or MSI installer or NuGet:
```csharp
PM> Install-Package GroupDocs.Merger
```

### Source PNG images

!["Sample1.png"](/merger/net/images/jpg/sample1.jpg)
!["Sample2.png"](/merger/net/images/jpg/sample2.jpg)
!["Sample3.png"](/merger/net/images/jpg/sample3.jpg)

### How to merge PNG files in horizontal mode

The following example demonstrates how to merge image files in horizontal mode with several lines of C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinoptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinmode) as a constructor parameter.
* Add another image file to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinoptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged image file as parameter.

```csharp
// Load the source image file
using (Merger merger = new Merger(@"c:\sample1.png"))
{
    // Define image join options with horizontal join mode
    ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Horizontal);
    // Add another image file to merge
    merger.Join(@"c:\sample2.png", joinOptions);
    // Add next image file to merge
    merger.Join(@"c:\sample3.png", joinOptions);
    // Merge image files and save result
    merger.Save(@"c:\merged.png");
}
```

### Result merged PNG image

!["Merged.png"](/merger/net/images/jpg/merged_horizontal.jpg)

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PNG Live Demo

GroupDocs.Merger for .NET provides an online [**PNG Merger App**](https://products.groupdocs.app/merger/png), which allows you to try it for free and check its quality and accuracy.