---
id: merge-images
url: merger/java/merge/images
title: Merge images
description: "Learn how to merge image files, combine image files into one file programmatically in Java language using GroupDocs.Merger for Java library."
keywords: Merge image files in Java, Combine image files programmatically
productName: GroupDocs.Merger for Java
weight: 1
structuredData:
    productCode: merger
    productPlatform: java
    appName: Merge image files in Java
    appDescription: Merge image in a quick and efficient way using java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge image files in Java 
        description: Learn how to merge image files in java language and GroupDocs.Merger for Java API, without the use of any third-party software like Microsoft or Open Office.
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

## How to merge image files in Java

[GroupDocs.Merger](https://products.groupdocs.com/merger/java) allows developers to combine multiple JPG documents in the preferred order and save them as a single file. You will not spend your time doing these operations manually on desktop software.
 With GroupDocs.Merger it is possible to combine image documents of any JPG, PNG or BMP extensions.

The following example demonstrates how to merge image files with several lines of Java code:

* Create an instance of [Merger](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class and pass enum value of [ImageJoinMode](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinMode) as a constructor parameter.
* Add another image file to merge with [join](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream)) method and pass instance of [ImageJoinOptions](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class [save](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and specify the filename for the merged image file as parameter.

```java
// Load the source image file
Merger merger = new Merger("c:\sample1.jpg")

// Define image join options with vertical join mode
ImageJoinOptions joinOptions = new ImageJoinOptions(ImageJoinMode.Vertical);
// Add another image file to merge
merger.join("c:\sample2.jpg", joinOptions);
// Merge image files and save result
merger.save("c:\merged.jpg");
```

### Merge different image file formats

This section describes how to merge different image file formats using GroupDocs.Merger API. Please look at the articles listed below:

* [How to merge JPG images in Java]({{< ref "merger/java/getting-started/use-cases/how-to-merge-jpg-images-using-java.md" >}})
* [How to merge PNG images in Java]({{< ref "merger/java/getting-started/use-cases/how-to-merge-png-images-using-java.md" >}})
* [How to merge BMP images in Java]({{< ref "merger/java/getting-started/use-cases/how-to-merge-bmp-images-using-java.md" >}})

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge Images Live Demo

GroupDocs.Merger for Java provides an online [**JPG Merger App**](https://products.groupdocs.app/merger/images/jpg) or  [**PNG Merger App**](https://products.groupdocs.app/merger/images/png) or  [**BMP Merger App**](https://products.groupdocs.app/merger/images/bmp), which allows you to try it for free and check its quality and accuracy.