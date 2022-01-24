---
id: merge-open-document
url: merger/net/merge/open-document
title: Merge Open Document files
description: "Learn how to merge Open Document files, combine ODT, ODS, ODP files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge ODT files in C#
    appDescription: Merge ODT in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge ODT files in C# 
        description: Learn how to merge ODT files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source ODT files 
          text: Create an instance of Merger class and pass source ODT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other ODT files
          text: Add other ODT files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge ODT files and save result 
          text: Call Merger class Save method and pass the filename for the resultant ODT file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

### About ODP File Format

ODT files are type of documents created with word processing applications that are based on OpenDocument Text File format. These are created with word processor applications such as free OpenOffice Writer and can hold content such as text, images, objects and styles. The ODT file is to Writer word processor what the DOCX is to Microsoft Word. Several applications including Google Docs and Google’s web-based word processor included with Google Drive can open the ODT files for editing. Microsoft Word can also open ODT files and save it in to other formats such as DOC and DOCX.

### About ODT File Format

ODT files are type of documents created with word processing applications that are based on OpenDocument Text File format. These are created with word processor applications such as free OpenOffice Writer and can hold content such as text, images, objects and styles. The ODT file is to Writer word processor what the DOCX is to Microsoft Word. Several applications including Google Docs and Google’s web-based word processor included with Google Drive can open the ODT files for editing. Microsoft Word can also open ODT files and save it in to other formats such as DOC and DOCX.

### About ODS File Format

Files with ODS extension stand for OpenDocument Spreadsheet Document format that is editable by the user. Data is stored inside the ODF file into rows and columns. It is an XML-based format and is one of the several subtypes in the Open Document Formats (ODF) family. The format is specified as part of the ODF 1.2 specifications published and maintained by OASIS.

## How to merge ODT files

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge ODT files when it's needed to organize multiple
 ODT files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine ODT documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge ODT files with several lines of C# code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source ODT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another ODT file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other ODT documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged ODT file as parameter.

```csharp
// Load the source ODT file
using (Merger merger = new Merger(@"c:\sample1.odt"))
{
    // Add another ODT file to merge
    merger.Join(@"c:\sample2.odt");
    // Merge ODT files ans save result
    merger.Save(@"c:\merged.odt");
}
```

NOTE:###############################################################3

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge ODT Live Demo

GroupDocs.Merger for .NET provides an online [**ODT Merger App**](https://products.groupdocs.app/merger/odt), which allows you to try it for free and check its quality and accuracy.
