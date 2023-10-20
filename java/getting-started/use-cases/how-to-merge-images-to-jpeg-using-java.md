---
id: how-to-merge-images-to-jpeg-using-java
url: merger/java/getting-started/use-cases/how-to-merge-images-to-jpeg-using-java
title: How to merge images to JPEG using Java
description: "Learn how to merge images to JPEG file, combine images into one JPEG file programmatically in Java language using GroupDocs.Merger for Java library."
keywords: Merge images to JPEG file in Java, Combine images to JPEG file programmatically
productName: GroupDocs.Merger for Java
weight: 7
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge images to JPEG file in Java
    appDescription: Merge images to JPEG file in a quick and efficient way using Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge images to JPEG file in Java 
        description: Learn how to merge images to JPEG file in Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-java
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

## JPEG Merger .NET API

[com.groupdocs.merger](https://products.groupdocs.com/merger/java) allows developers to combine multiple image documents in the preferred order and save them as a single JPEG file.

## About JPEG File Format

JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image. The higher the compression value, the higher the degradation in image quality.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/java) to download API jar package and add it to the .pom file. :
```java
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-merger</artifactId>
    <version>23.2</version>
</dependency>
```

### Source images

!["Sample1.jpg"](/merger/net/images/jpg/sample1.jpg)
!["Sample2.jpg"](/merger/net/images/jpg/sample2.jpg)
!["Sample3.jpg"](/merger/net/images/jpg/sample3.jpg)

### How to merge images to JPEG file

The following example demonstrates how to merge images to JPEG file with several lines of Java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinoptions/) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinmode/) as a constructor parameter.
* Add another image file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#Merger-java.io.InputStream-) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/imagejoinoptions/) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and specify the filename for the merged image file as parameter.

```java
// Load the source image file
Merger merger = new Merger("c:\sample1.jpeg")
{
    // Define image join options with horizontal join mode
    ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Horizontal);
    // Add another image file to merge
    merger.join("c:\sample2.png", joinOptions);
    // Define image join options with vertical join mode
    ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Vertical);
    // Add next image file to merge
    merger.join("c:\sample3.bmp", joinOptions);
    // Merge image files and save result
    merger.save("c:\merged.jpeg");
}
```

### Result merged JPEG image

!["Merged.jpeg"](/merger/net/images/jpg/merged_grid.jpg)

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge JPEG Live Demo

GroupDocs.Merger for Java provides an online [**Image to JPEG Merger App**](https://products.groupdocs.app/merger/image-to-jpeg), which allows you to try it for free and check its quality and accuracy.