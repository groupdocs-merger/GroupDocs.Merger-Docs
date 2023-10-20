---
id: how-to-merge-tiff-images-using-java
url: merger/java/getting-started/use-cases/how-to-merge-tiff-images-using-java
title: How to merge TIFF images using java
description: "Learn how to merge TIFF image files, combine TIFF image files into one file programmatically in java language using GroupDocs.Merger for Java library."
keywords: Merge TIFF image files in java, Combine TIFF image files programmatically
productName: GroupDocs.Merger for Java
weight: 6
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge TIFF image files in java
    appDescription: Merge TIFF image in a quick and efficient way using java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge TIFF image files in java 
        description: Learn how to merge TIFF image files in java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source image files 
          text: Create an instance of Merger class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/java/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other image files
          text: Add other image files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/java/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge image files and save result 
          text: Call Merger class Save method and pass the filename for the resultant image file as parameter.
          imageUrl: merger/java/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## TIFF Merger Java API

[GroupDocs.Merger](https://products.groupdocs.com/merger/java) allows developers to combine multiple TIFF documents in the preferred order and save them as a single file.

## About TIFF File Format

TIFF, Tag Image File Format, is a computer file used to store raster graphics and image information. A favorite among photographers, TIFFs are a handy way to store high-quality images before editing if you want to avoid lossy file formats.

### Download and Configure

You can follow the steps below to reference GroupDocs.Merger for Java downloaded from official website [Downloads section](https://downloads.groupdocs.com/merger/java):

1. Unpack zip archive .
2. Switch to **lib** folder.
3. Run **install.bat** (for Windows) or **install.sh** (for Linux) file to install the library in your local maven repository.
4. After this you should add the merger **dependency** block to your *pom.xm*l project file.

### Source TIFF images

!["Sample1.tiff"](/merger/java/images/jpg/sample1.jpg)
!["Sample2.tiff"](/merger/java/images/jpg/sample2.jpg)
!["Sample3.tiff"](/merger/java/images/jpg/sample3.jpg)

### How to merge TIFF files in vertical mode

The following example demonstrates how to merge image files in vertical mode with several lines of java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinoptions/) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinmode/) as a constructor parameter.
* Add another image file to merge with [Join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinoptions/) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [Save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and specify the filename for the merged image file as parameter.

```java
// Load the source image file
Merger merger = new Merger("c:\sample1.tiff")

// Define image join options with vertical join mode
ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Vertical);
// Add another image file to merge
merger.join("c:\sample2.tiff", joinOptions);
// Add next image file to merge
merger.join("c:\sample3.tiff", joinOptions);
// Merge image files and save result
merger.save("c:\merged.tiff");

```

### Result merged TIFF image

!["Merged.tiff"](/merger/java/images/jpg/merged_vertical.jpg)

### Code Examples

Please find more [use-cases and complete java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge TIFF Live Demo

GroupDocs.Merger for Java provides an online [**TIFF Merger App**](https://products.groupdocs.app/merger/tiff), which allows you to try it for free and check its quality and accuracy.