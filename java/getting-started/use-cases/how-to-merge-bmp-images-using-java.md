---
id: how-to-merge-bmp-images-using-java
url: merger/java/getting-started/use-cases/how-to-merge-bmp-images-using-java
title: How to merge BMP images using Java
description: "Learn how to merge BMP image files, combine BMP image files into one file programmatically in java language using GroupDocs.Merger for Java library."
keywords: Merge BMP image files in Java, Combine BMP image files programmatically
productName: GroupDocs.Merger for Java
weight: 3
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge BMP image files in Java
    appDescription: Merge BMP image in a quick and efficient way using java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge BMP image files in Java 
        description: Learn how to merge BMP image files in java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source image files 
          text: Create an instance of Merger class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/java/images/merge-files-step-1.bmp
          imageHeight: 157
          imageWidth: 645
        - name: Add other image files
          text: Add other image files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/java/images/merge-files-step-2.bmp
          imageHeight: 144
          imageWidth: 603
        - name: Merge image files and save result 
          text: Call Merger class Save method and pass the filename for the resultant image file as parameter.
          imageUrl: merger/java/images/merge-files-step-3.bmp
          imageHeight: 151
          imageWidth: 646
---

## BMP Merger Java API

[GroupDocs.Merger](https://products.groupdocs.com/merger/java) allows developers to combine multiple BMP documents in the preferred order and save them as a single file.

## About BMP File Format

Files having extension .BMP represent Bitmap Image files that are used to store bitmap digital images. These images are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency serves the purpose of opening the file on multiple platforms such as Microsoft Windows and Mac. The BMP file format can store data as two-dimensional digital images in both monochrome as well as color format with various colour depths.

### Download and Configure

You can follow the steps below to reference GroupDocs.Merger for Java downloaded from official website [Downloads section](https://downloads.groupdocs.com/merger/java):

1. Unpack zip archive .
2. Switch to **lib** folder.
3. Run **install.bat** (for Windows) or **install.sh** (for Linux) file to install the library in your local maven repository.
4. After this you should add the merger **dependency** block to your *pom.xm*l project file.

### Source BMP images

!["Sample1.bmp"](/merger/java/images/jpg/sample1.jpg)
!["Sample2.bmp"](/merger/java/images/jpg/sample2.jpg)
!["Sample3.bmp"](/merger/java/images/jpg/sample3.jpg)

### How to merge BMP files in vertical mode

The following example demonstrates how to merge image files in vertical mode with several lines of java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinMode) as a constructor parameter.
* Add another image file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream)) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and specify the filename for the merged image file as parameter.

```java
// Load the source image file
Merger merger = new Merger("c:\sample1.bmp")

// Define image join options with vertical join mode
ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Vertical);
// Add another image file to merge
merger.join("c:\sample2.bmp", joinOptions);
// Add next image file to merge
merger.join("c:\sample3.bmp", joinOptions);
// Merge image files and save result
merger.save("c:\merged.bmp");
```

### Result merged BMP image

!["Merged.bmp"](/merger/java/images/jpg/merged_vertical.jpg)

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge BMP Live Demo

GroupDocs.Merger for Java provides an online [**BMP Merger App**](https://products.groupdocs.app/merger/images/bmp), which allows you to try it for free and check its quality and accuracy.