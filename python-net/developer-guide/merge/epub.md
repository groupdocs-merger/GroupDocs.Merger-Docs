---
id: merge-epub
url: merger/python-net/merge/epub
title: Merge EPUB
description: "Learn how to merge EPUB files, combine EPUB files into one file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge EPUB files in Python via .NET, Combine EPUB files programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 23
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge EPUB files in Python via .NET
    appDescription: Merge EPUB in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge EPUB files in Python via .NET 
        description: Learn how to merge EPUB files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source EPUB files 
          text: Create an instance of Merger class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other EPUB files
          text: Add other EPUB files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge EPUB files and save result 
          text: Call Merger class Save method and pass the filename for the resultant EPUB file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge EPUB files in Python via .NET

You can easily combine multiple EPUB files into one using [GroupDocs.Merger](https://products.groupdocs.com/merger/python-net) library API and all the files content will be preserved.
The following example demonstrates how to merge EPUB files with several lines of C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another EPUB file to merge with [join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join) method. Repeat this step for other EPUB documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged EPUB file as parameter.

```python
with gm.Merger("c:/sample1.epub") as merger:
    merger.join("c:/sample2.epub")
    merger.save("c:/merged.epub")
```

### About EPUB File Format 

Files with .EPUB extension are an e-book file format that provide a standard digital publication format for publishers and consumers. The format has been so common by now that it is supported by many e-readers and software applications. For example, on Mac OS, the pre-installed Books software provides the support for opening such files. In addition, there are a lot of compatible software available for smartphones, tablets and computers.

### Code Examples

Please find more [use-cases and complete net sources]({{< ref "merger/python-net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge EPUB Live Demo 

GroupDocs.Merger for Python via .NET provides an online [**EPUB Merger App**](https://products.groupdocs.app/merger/epub), which allows you to try it for free and check its quality and accuracy.

[!["Merge EPUB"](/merger/net/images/merge/merge-epub.png)](https://products.groupdocs.app/merger/epub)