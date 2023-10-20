---
id: how-to-merge-gif-images-using-csharp
url: merger/net/getting-started/use-cases/how-to-merge-gif-images-using-csharp
title: How to merge GIF images using C#
description: "Learn how to merge GIF image files, combine GIF image files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge GIF image files in C#, Combine GIF image files programmatically
productName: GroupDocs.Merger for .NET
weight: 4
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge GIF image files in C#
    appDescription: Merge GIF image in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge GIF image files in C# 
        description: Learn how to merge GIF image files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
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

## GIF Merger .NET API

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to combine multiple GIF documents in the preferred order and save them as a single file.

## About GIF File Format

GIF, Graphics Interchange Format, is a raster file format designed for relatively basic images that appear mainly on the internet. Each file can support up to 8 bits per pixel and can contain 256 indexed colors. GIF files also allow images or frames to be combined, creating basic animations.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/net) to download API DLLs or MSI installer or NuGet:
```csharp
PM> Install-Package GroupDocs.Merger
```

### Source GIF images

!["Sample1.gif"](/merger/net/images/jpg/sample1.jpg)
!["Sample2.gif"](/merger/net/images/jpg/sample2.jpg)
!["Sample3.gif"](/merger/net/images/jpg/sample3.jpg)

### How to merge GIF files in horizontal mode

The following example demonstrates how to merge image files in horizontal mode with several lines of C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinoptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinmode) as a constructor parameter.
* Add another image file to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinoptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged image file as parameter.

```csharp
// Load the source image file
using (Merger merger = new Merger(@"c:\sample1.gif"))
{
    // Define image join options with horizontal join mode
    ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Horizontal);
    // Add another image file to merge
    merger.Join(@"c:\sample2.gif", joinOptions);
    // Add next image file to merge
    merger.Join(@"c:\sample3.gif", joinOptions);
    // Merge image files and save result
    merger.Save(@"c:\merged.gif");
}
```

### Result merged GIF image

!["Merged.png"](/merger/net/images/jpg/merged_horizontal.jpg)

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge GIF Live Demo

GroupDocs.Merger for .NET provides an online [**GIF Merger App**](https://products.groupdocs.app/merger/gif), which allows you to try it for free and check its quality and accuracy.