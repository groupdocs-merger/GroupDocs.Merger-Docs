---
id: how-to-merge-png-images-using-nodejs-java
url: merger/nodejs-java/getting-started/use-cases/how-to-merge-png-images-using-nodejs-java
title: How to merge PNG images using Node.js via Java
description: "Learn how to merge PNG image files, combine PNG image files into one file programmatically in nodejs-java language using GroupDocs.Merger for Node.js via Java library."
keywords: Merge PNG image files in Node.js via Java, Combine PNG image files programmatically
productName: GroupDocs.Merger for Node.js via Java
weight: 3
structuredData:
    productCode: merger
    productPlatform: nodejs-java
    appName: Merge PNG image files in Node.js via Java
    appDescription: Merge PNG image in a quick and efficient way using nodejs-java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PNG image files in Node.js via Java 
        description: Learn how to merge PNG image files in nodejs-java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
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

## PNG Merger Node.js via Java API

[GroupDocs.Merger](https://products.groupdocs.com/merger/nodejs-java) allows developers to combine multiple PNG documents in the preferred order and save them as a single file.

## About PNG File Format

Files having extension .PNG represent Bitmap Image files that are used to store bitmap digital images. These images are independent of graphics adapter and are also called device independent bitmap (DIB) file format. This independency serves the purpose of opening the file on multiple platforms such as Microsoft Windows and Mac. The PNG file format can store data as two-dimensional digital images in both monochrome as well as color format with various colour depths.

### Download and Configure

You can download GroupDocs.Merger for Node.js via Java from official website [Downloads section](https://downloads.groupdocs.com/merger/nodejs-java).

### Source PNG images

!["Sample1.png"](/merger/java/images/jpg/sample1.jpg)
!["Sample2.png"](/merger/java/images/jpg/sample2.jpg)
!["Sample3.png"](/merger/java/images/jpg/sample3.jpg)

### How to merge PNG files in vertical mode

The following example demonstrates how to merge image files in vertical mode with several lines of nodejs-java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Create an instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class and pass enum value of [ImageJoinMode](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinMode) as a constructor parameter.
* Add another image file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream)) method and pass instance of [ImageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/ImageJoinOptions) class as a method parameter. Repeat this step for other image documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and specify the filename for the merged image file as parameter.

```js
const merger = new groupdocs.merger.Merger('c:/sample1.png');
const imageJoinModeVertical = groupdocs.merger.ImageJoinMode.Vertical;
const imageJoinOptions = new groupdocs.merger.ImageJoinOptions(imageJoinModeVertical);
merger.join('c:/sample2.png', imageJoinOptions);
merger.join('c:/sample3.png', imageJoinOptions);
return merger.save('c:/merged.png');
```

### Result merged PNG image

!["Merged.png"](/merger/java/images/jpg/merged_vertical.jpg)

### Code Examples

Please find more [use-cases and complete Node.js via Java sources]({{< ref "merger/nodejs-java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PNG Live Demo

GroupDocs.Merger for Node.js via Java provides an online [**PNG Merger App**](https://products.groupdocs.app/images/png), which allows you to try it for free and check its quality and accuracy.