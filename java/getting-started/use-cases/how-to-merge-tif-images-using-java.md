---
id: how-to-merge-tif-images-using-java
url: merger/java/getting-started/use-cases/how-to-merge-tif-images-using-java
title: How to merge TIF images using java
description: "Learn how to merge TIF image files, combine TIF image files into one file programmatically in java language using GroupDocs.Merger for Java library."
keywords: Merge TIF image files in java, Combine TIF image files programmatically
productName: GroupDocs.Merger for Java
weight: 5
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge TIF image files in java
    appDescription: Merge TIF image in a quick and efficient way using java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge TIF image files in java 
        description: Learn how to merge TIF image files in java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
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

## TIF Merger Java API

[GroupDocs.Merger](https://products.groupdocs.com/merger/java) allows developers to combine multiple TIF documents in the preferred order and save them as a single file.

### About TIF File Format

TIF (or TIFF) is an image format used for containing high quality graphics. It stands for “Tagged Image File Format” or “Tagged Image Format”. The format was created by Aldus Corporation but Adobe acquired the format later and made subsequent update in this format. TIF file is capable of holding both lossy jpeg compression and lossless image data. It can also contain vector based graphics data. TIF file format is widely supported in image editing applications. For that it’s a very popular image format among Graphic artists, Photographers, and Publishing authorities. PaintShop Pro is one of the most popular applications available for handling TIF images.

### Download and Configure

You can follow the steps below to reference GroupDocs.Merger for Java downloaded from official website [Downloads section](https://downloads.groupdocs.com/merger/java):

1. Unpack zip archive .
2. Switch to **lib** folder.
3. Run **install.bat** (for Windows) or **install.sh** (for Linux) file to install the library in your local maven repository.
4. After this you should add the merger **dependency** block to your *pom.xm*l project file.

## How to merge TIF files
The following example demonstrates how to merge TIF files with several lines of java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class and pass source TIF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another TIF file to merge with [Join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) method. Repeat this step for other TIF documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [Save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and specify the filename for the merged TIF file as parameter.

```java
// Load the source TIF file
Merger merger = new Merger("c:\sample1.tif")

// Add another TIF file to merge
merger.join("c:\sample2.tif");
// Merge TIF files and save result
merger.save("c:\merged.tif");

```

NOTE: You may merge other TIF formats like TIFF in the same way as shown above. For this provide files by specifying their names with extension.

### Code Examples

Please find more [use-cases and complete java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge TIF Live Demo

GroupDocs.Merger for Java provides an online [**TIF Merger App**](https://products.groupdocs.app/merger/tif), which allows you to try it for free and check its quality and accuracy.
