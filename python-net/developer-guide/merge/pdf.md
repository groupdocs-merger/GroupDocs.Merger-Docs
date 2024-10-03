---
id: merge-pdf
url: merger/python-net/merge-pdf
title: Merge PDF
description: "Follow this guide and learn how to merge PDF files, combine several PDFs into one using GroupDocs.Merger for Python via .NET API and couple lines of code"
keywords: Merge PDF, Combine PDF, Join PDF, Merge PDF with GroupDocs.Merger for Python via .NET
productName: GroupDocs.Merger for Python via .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge PDF files in Python via .NET
    appDescription: Merge PDF in a quick and efficient way using Python via .NET language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PDF files in Python via .NET 
        description: Learn how to merge PDF files in Python via .NET language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-net
        steps:
        - name: Load source PDF files 
          text: Create an instance of Merger class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 159
          imageWidth: 603
        - name: Add other PDF files
          text: Add other PDF files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 159
          imageWidth: 603
        - name: Merge PDF files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PDF file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 159
          imageWidth: 603
---

## How to merge PDF files in Python via .NET

**[GroupDocs.Merger](https://products.groupdocs.com/merger/python-net)**  allows developers to merge PDF files when it's needed to organize multiple
 PDF files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine PDF documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge PDF files with several lines of Python via .NET code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PDF file to merge with [join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join) method. Repeat this step for other PDF documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged PDF file as parameter.

```python
with gm.Merger("c:/sample1.pdf") as merger:
    merger.join("c:/sample2.pdf")
    merger.save("c:/merged.pdf")
```

### About PDF File Format

Portable Document Format (PDF) is a type of document created by Adobe back in the 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

### Code Examples

Please find more [use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PDF Live Demo

GroupDocs.Merger for Python via .NET provides an online [**PDF Merger App**](https://products.groupdocs.app/merger/pdf), which allows you to try it for free and check its quality and accuracy.

[!["Merge PDF"](/merger/net/images/merge/merge-pdf.png)](https://products.groupdocs.app/merger/pdf)