---
id: merge-images
url: merger/net/merge/images
title: Merge images
description: "Learn how to merge image files, combine image files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge image files in C#, Combine image files programmatically
productName: GroupDocs.Merger for .NET
weight: 20
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge image files in C#
    appDescription: Merge image in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge image files in C# 
        description: Learn how to merge image files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
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

## How to merge image files in C\#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to combine multiple JPG documents in the preferred order and save them as a single file. You will not spend your time doing these operations manually on desktop software.
 With GroupDocs.Merger it is possible to combine image documents of any JPG, PNG or BMP extensions.

The following example demonstrates how to merge image files with several lines of C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinoptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinmode) as a constructor parameter.
* Add another image file to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/imagejoinoptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged image file as parameter.

```csharp
// Load the source image file
using (Merger merger = new Merger(@"c:\sample1.jpg"))
{
    // Define image join options with vertical join mode
    ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Vertical);
    // Add another image file to merge
    merger.Join(@"c:\sample2.jpg", joinOptions);
    // Merge image files and save result
    merger.Save(@"c:\merged.jpg");
}
```

### Merge different image file formats

This section describes how to merge different image file formats using GroupDocs.Merger API. Please look at the articles listed below:

* [How to merge JPG images in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-jpg-images-using-csharp.md" >}})
* [How to merge PNG images in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-png-images-using-csharp.md" >}})
* [How to merge BMP images in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-bmp-images-using-csharp.md" >}})
* [How to merge TIF images in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-tif-images-using-csharp.md" >}})
* [How to merge GIF images in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-gif-images-using-csharp.md" >}})
* [How to merge TIFF images in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-tiff-images-using-csharp.md" >}})

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge Images Live Demo

GroupDocs.Merger offers the following free online tools to test its quality and accuracy:
* [**JPG Merger App**](https://products.groupdocs.app/merger/jpg)
* [**PNG Merger App**](https://products.groupdocs.app/merger/png)
* [**BMP Merger App**](https://products.groupdocs.app/merger/bmp)
* [**GIF Merger App**](https://products.groupdocs.app/merger/gif)
* [**TIFF Merger App**](https://products.groupdocs.app/merger/tiff)