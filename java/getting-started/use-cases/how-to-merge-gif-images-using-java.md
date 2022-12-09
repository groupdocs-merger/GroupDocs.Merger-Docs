---
id: how-to-merge-gif-images-using-java
url: merger/java/getting-started/use-cases/how-to-merge-gif-images-using-java
title: How to merge BMP images using Java
description: "Learn how to merge GIF image files, combine GIF image files into one file programmatically in java language using GroupDocs.Merger for Java library."
keywords: Merge GIF image files in Java, Combine GIF image files programmatically
productName: GroupDocs.Merger for Java
weight: 3
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge GIF image files in Java
    appDescription: Merge GIF image in a quick and efficient way using java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge GIF image files in Java 
        description: Learn how to merge GIF image files in java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
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

## GIF Merger Java API

[GroupDocs.Merger](https://products.groupdocs.com/merger/java) allows developers to combine multiple GIF documents in the preferred order and save them as a single file.

## About GIF File Format

GIF, Graphics Interchange Format, is a raster file format designed for relatively basic images that appear mainly on the internet. Each file can support up to 8 bits per pixel and can contain 256 indexed colors. GIF files also allow images or frames to be combined, creating basic animations.

### Download and Configure

You can follow the steps below to reference GroupDocs.Merger for Java downloaded from official website [Downloads section](https://downloads.groupdocs.com/merger/java):

1. Unpack zip archive .
2. Switch to **lib** folder.
3. Run **install.bat** (for Windows) or **install.sh** (for Linux) file to install the library in your local maven repository.
4. After this you should add the merger **dependency** block to your *pom.xm*l project file.

### Source GIF images

!["Sample1.gif"](/merger/java/images/jpg/sample1.jpg)
!["Sample2.gif"](/merger/java/images/jpg/sample2.jpg)
!["Sample3.gif"](/merger/java/images/jpg/sample3.jpg)

### How to merge GIF files in horizontal mode

The following example demonstrates how to merge image files in horizontal mode with several lines of java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinoptions/) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinmode/) as a constructor parameter.
* Add another image file to merge with [Join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinoptions/) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [Save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and specify the filename for the merged image file as parameter.

```java
// Load the source image file
Merger merger = new Merger("c:\sample1.gif")

// Define image join options with horizontal join mode
ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Horizontal);
// Add another image file to merge
merger.join("c:\sample2.gif", joinOptions);
// Add next image file to merge
merger.join("c:\sample3.gif", joinOptions);
// Merge image files and save result
merger.save("c:\merged.gif");

```

### Result merged GIF image

!["Merged.png"](/merger/java/images/jpg/merged_horizontal.jpg)

### Code Examples

Please find more [use-cases and complete java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge GIF Live Demo

GroupDocs.Merger for Java provides an online [**GIF Merger App**](https://products.groupdocs.app/merger/images/gif), which allows you to try it for free and check its quality and accuracy.