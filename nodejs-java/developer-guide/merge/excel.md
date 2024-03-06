---
id: merge-excel
url: merger/nodejs-java/merge/excel
title: Merge Excel spreadsheets
linkTitle: Merge Excel
weight: 4
description: "Follow this guide and learn how to merge MS Excel spreadsheets using Node.js via Java programming language."
keywords: Merge Excel files, Merge Spreadsheets, Merge XLS, Merge XLSX
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
toc: True
structuredData:
    productCode: merger
    productPlatform: nodejs-java
    appName: Merge XLSX files in Node.js via Java
    appDescription: Merge XLSX in a quick and efficient way using java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLSX in Node.js via Java 
        description: Learn how to merge XLSX in Node.js via Java language and GroupDocs.Merger for Node.js via Java API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/nodejs-java/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-nodejs-java
        steps:
        - name: Load source XLSX files 
          text: Create an instance of Merger class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/java/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLSX files
          text: Add other XLSX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/java/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLSX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant XLSX file as parameter.
          imageUrl: merger/java/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

A **spreadsheet** file contains data in the form of rows and columns. A spreadsheet file can be saved in several different file formats, each having a different file extension for unique representation. Data is stored in cells either in plain form such as text string, numbers, date, currency, etc. or as formulas that change a cell’s value when referenced cell values change.

Common spreadsheet file extensions and their file formats include **XLSX** (Microsoft Excel Open XML Spreadsheet), **ODS** (OpenDocument Spreadsheet) and **XLS** (Microsoft Excel Binary File Format).

XLSX is well-known format for Microsoft Excel documents that was introduced by Microsoft with the release of Microsoft Office 2007. Based on structure organized according to the Open Packaging Conventions as outlined in Part 2 of the OOXML standard ECMA-376, the new format is a zip package that contains a number of XML files. The underlying structure and files can be examined by simply unzipping the .xlsx file.

## How to merge XLSX files programmatically

[GroupDocs.Merger](https://products.groupdocs.com/merger/nodejs-java) allows developers to merge XLSX files when it's needed to organize multiple
 XLSX files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine XLSX documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge XLSX files with several lines of java code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another XLSX file to merge with [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream)) method. Repeat this step for other XLSX documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and specify the filename for the merged XLSX file as parameter.

```java
const merger = new groupdocs.merger.Merger('c:/sample1.xlsx');
merger.join('c:/sample2.xlsx');
merger.save('c:/merged.xlsx');
```

### Code Examples

Please find more [use-cases and complete Node.js via Java sources]({{< ref "merger/nodejs-java/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge XLSX Live Demo

GroupDocs.Merger for Node.js via Java provides an online [**XLSX Merger App**](https://products.groupdocs.app/merger/xlsx), which allows you to try it for free and check its quality and accuracy.
