---
id: how-to-merge-png-images-using-python-net
url: merger/python-net/getting-started/use-cases/how-to-merge-png-images-using-python-net
title: How to merge PNG images using Python via .NET
description: "Learn how to merge PNG image files, combine PNG image files into one file programmatically in python-net language using GroupDocs.Merger for Python via .NET library."
keywords: Merge PNG image files in Python via .NET, Combine PNG image files programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 3
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge PNG image files in Python via .NET
    appDescription: Merge PNG image in a quick and efficient way using python-net language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PNG image files in Python via .NET 
        description: Learn how to merge PNG image files in python-net language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
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

## PNG Merger Python via .NET API

[GroupDocs.Merger](https://products.groupdocs.com/merger/python-net) allows developers to combine multiple PNG documents in the preferred order and save them as a single file.

## About PNG File Format

Files having extension .PNG represent Bitmap Image files that are used to store bitmap digital images. These images are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency serves the purpose of opening the file on multiple platforms such as Microsoft Windows and Mac. The PNG file format can store data as two-dimensional digital images in both monochrome as well as color format with various colour depths.

### Download and Configure

You can download GroupDocs.Merger for Python via .NET from official website [Downloads section](https://downloads.groupdocs.com/merger/python-net).

### Source PNG images

!["Sample1.png"](/merger/net/images/jpg/sample1.jpg)
!["Sample2.png"](/merger/net/images/jpg/sample2.jpg)
!["Sample3.png"](/merger/net/images/jpg/sample3.jpg)

### How to merge PNG files in vertical mode

The following example demonstrates how to merge image files in vertical mode with several lines of python-net code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/ImageJoinOptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/ImageJoinMode) as a constructor parameter.
* Add another image file to merge with [join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/ImageJoinOptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged image file as parameter.

```python
with gm.Merger("c:/sample1.png") as merger:
    image_join_mode = gm.domain.options.ImageJoinMode.VERTICAL
    image_join_options = gm.domain.options.ImageJoinOptions(image_join_mode)
    merger.join("c:/sample2.png", join_options = image_join_options)
    merger.join("c:/sample3.png", join_options = image_join_options)
    merger.save("c:/merged.png")
```

### Result merged PNG image

!["Merged.png"](/merger/net/images/jpg/merged_vertical.jpg)

### Code Examples

Please find more [use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PNG Live Demo

GroupDocs.Merger for Python via .NET provides an online [**PNG Merger App**](https://products.groupdocs.app/images/png), which allows you to try it for free and check its quality and accuracy.