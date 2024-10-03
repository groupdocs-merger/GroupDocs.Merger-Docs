---
id: merge-images
url: merger/python-net/merge/images
title: Merge images
description: "Learn how to merge image files, combine image files into one file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge image files in Python via .NET, Combine image files programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge image files in Python via .NET
    appDescription: Merge image in a quick and efficient way using net language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge image files in Python via .NET 
        description: Learn how to merge image files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
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

## How to merge image files in Python via .NET

[GroupDocs.Merger](https://products.groupdocs.com/merger/python-net) allows developers to combine multiple JPG documents in the preferred order and save them as a single file. You will not spend your time doing these operations manually on desktop software.
 With GroupDocs.Merger it is possible to combine image documents of any JPG, PNG or BMP extensions.

The following example demonstrates how to merge image files with several lines of Python via .NET code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/ImageJoinOptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/ImageJoinMode) as a constructor parameter.
* Add another image file to merge with [join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/ImageJoinOptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged image file as parameter.

```python
with gm.Merger("c:/sample1.jpg") as merger:
    image_join_mode = gm.domain.options.ImageJoinMode.HORIZONTAL
    image_join_options = gm.domain.options.ImageJoinOptions(image_join_mode)
    merger.join("c:/sample2.jpg", join_options = image_join_options)
    merger.save("c:/merged.jpg")
```

### Merge different image file formats

This section describes how to merge different image file formats using GroupDocs.Merger API. Please look at the articles listed below:

* [How to merge JPG images in Python via .NET]({{< ref "merger/python-net/getting-started/use-cases/how-to-merge-jpg-images-using-python-net.md" >}})
* [How to merge PNG images in Python via .NET]({{< ref "merger/python-net/getting-started/use-cases/how-to-merge-png-images-using-python-net.md" >}})
* [How to merge BMP images in Python via .NET]({{< ref "merger/python-net/getting-started/use-cases/how-to-merge-bmp-images-using-python-net.md" >}})

### Code Examples

Please find more [use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge Images Live Demo

GroupDocs.Merger offers the following free online tools to test its quality and accuracy:
* [**JPG Merger App**](https://products.groupdocs.app/merger/jpg)
* [**PNG Merger App**](https://products.groupdocs.app/merger/png)
* [**BMP Merger App**](https://products.groupdocs.app/merger/bmp)