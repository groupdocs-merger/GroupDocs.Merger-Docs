---
id: merge-images
url: merger/nodejs-java/merge/images
title: Merge images
description: "Learn how to merge image files, combine image files into one file programmatically in Node.js via Java language using GroupDocs.Merger for Node.js via Java library."
keywords: Merge image files in Node.js via Java, Combine image files programmatically
productName: GroupDocs.Merger for Node.js via Java
weight: 1
structuredData:
    productCode: merger
    productPlatform: nodejs-java
    appName: Merge image files in Node.js via Java
    appDescription: Merge image in a quick and efficient way using java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge image files in Node.js via Java 
        description: Learn how to merge image files in Node.js via Java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/nodejs-java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-nodejs-java
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

## How to merge image files in Node.js via Java

[GroupDocs.Merger](https://products.groupdocs.com/merger/nodejs-java) allows developers to combine multiple JPG documents in the preferred order and save them as a single file. You will not spend your time doing these operations manually on desktop software.
 With GroupDocs.Merger it is possible to combine image documents of any JPG, PNG or BMP extensions.

The following example demonstrates how to merge image files with several lines of Node.js via Java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinMode) as a constructor parameter.
* Add another image file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream)) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and specify the filename for the merged image file as parameter.

```java
const merger = new groupdocs.merger.Merger('c:/sample1.jpg');
const imageJoinModeVertical = groupdocs.merger.ImageJoinMode.Vertical;
const imageJoinOptions = new groupdocs.merger.ImageJoinOptions(imageJoinModeVertical);
merger.join('c:/sample2.jpg', imageJoinOptions);
merger.save('c:/merged.jpg');
```

### Merge different image file formats

This section describes how to merge different image file formats using GroupDocs.Merger API. Please look at the articles listed below:

* [How to merge JPG images in Node.js via Java]({{< ref "merger/nodejs-java/getting-started/use-cases/how-to-merge-jpg-images-using-nodejs-java.md" >}})
* [How to merge PNG images in Node.js via Java]({{< ref "merger/nodejs-java/getting-started/use-cases/how-to-merge-png-images-using-nodejs-java.md" >}})
* [How to merge BMP images in Node.js via Java]({{< ref "merger/nodejs-java/getting-started/use-cases/how-to-merge-bmp-images-using-nodejs-java.md" >}})

### Code Examples

Please find more [use-cases and complete Node.js via Java sources]({{< ref "merger/nodejs-java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge Images Live Demo

GroupDocs.Merger offers the following free online tools to test its quality and accuracy:
* [**JPG Merger App**](https://products.groupdocs.app/merger/jpg)
* [**PNG Merger App**](https://products.groupdocs.app/merger/png)
* [**BMP Merger App**](https://products.groupdocs.app/merger/bmp)