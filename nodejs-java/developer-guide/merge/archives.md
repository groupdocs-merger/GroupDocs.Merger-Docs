---
id: merge-archives
url: merger/nodejs-java/merge/archives
title: Merge archives
description: "Learn how to merge archive files, combine archive files into one file programmatically in Node.js via Java language using GroupDocs.Merger for Node.js via Java library."
keywords: Merge archive files in Node.js via Java, Combine archive files programmatically
productName: GroupDocs.Merger for Node.js via Java
toc: True
weight: 15
structuredData:
    productCode: merger
    productPlatform: nodejs-java
    appName: Merge archive files in Node.js via Java
    appDescription: Merge archive in a quick and efficient way using Node.js via Java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge archive files in Node.js via Java 
        description: Learn how to merge archive files in Node.js via Java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/nodejs-java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-nodejs-java
        steps:
        - name: Load source archive files 
          text: Create an instance of Merger class and pass source archive file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          archiveUrl: merger/java/archives/merge-files-step-1.png
          archiveHeight: 157
          archiveWidth: 645
        - name: Add other archive files
          text: Add other archive files you want to merge into a single document with Join method of Merger class.
          archiveUrl: merger/java/archives/merge-files-step-2.png
          archiveHeight: 144
          archiveWidth: 603
        - name: Merge archive files and save result 
          text: Call Merger class Save method and pass the filename for the resultant archive file as parameter.
          archiveUrl: merger/java/archives/merge-files-step-3.png
          archiveHeight: 151
          archiveWidth: 646
---

## How to merge archive files in Node.js via Java

[GroupDocs.Merger](https://products.groupdocs.com/merger/nodejs-java) allows developers to combine multiple ZIP documents in the preferred order and save them as a single file. You will not spend your time doing these operations manually on desktop software.
 With GroupDocs.Merger it is possible to combine archive documents of any archive extensions such as ZIP or TAR.

The following example demonstrates how to merge archive files with several lines of Node.js via Java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class and pass source archive file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another archive file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.lang.String-) method. Repeat this step for other archive documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and specify the filename for the merged archive file as parameter.

```js
const inputFilePath = `c:/sample1.zip`;
const merger = new groupdocs.merger.Merger(inputFilePath);
const outputPath = `c:/merged.zip`;
merger.join('c:/sample2.zip');
merger.save(outputPath);
```

### Merge different archive file formats

This section describes how to merge different archive file formats using GroupDocs.Merger API. Please look at the articles listed below:

* [How to merge archives to ZIP in Node.js via Java]({{< ref "merger/nodejs-java/getting-started/use-cases/how-to-merge-archives-to-zip-using-nodejs-java.md" >}})

### Code Examples

Please find more [use-cases and complete Node.js via Java sources]({{< ref "merger/nodejs-java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge Archives Live Demo

GroupDocs.Merger for Node.js via Java provides online [**ZIP Merger App**](https://products.groupdocs.app/merger/zip) and [**TAR Merger App**](https://products.groupdocs.app/merger/tar), which allow you to try it for free and check its quality and accuracy.