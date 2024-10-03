---
id: how-to-merge-archives-to-zip-using-python-net
url: merger/python-net/getting-started/use-cases/how-to-merge-archives-to-zip-using-python-net
title: How to merge archives to ZIP using Python via .NET
description: "Learn how to merge archives to ZIP file, combine archives into one ZIP file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge archives to ZIP file in Python via .NET, Combine archives to ZIP file programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 7
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge archives to ZIP file in Python via .NET
    appDescription: Merge archives to ZIP file in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge archives to ZIP file in Python via .NET 
        description: Learn how to merge archives to ZIP file in Python via .NET language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source archive files 
          text: Create an instance of Merger class and pass source archive file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          archiveUrl: merger/net/archives/merge-files-step-1.png
          archiveHeight: 157
          archiveWidth: 645
        - name: Add other archive files
          text: Add other archive files you want to merge into a single document with Join method of Merger class.
          archiveUrl: merger/net/archives/merge-files-step-2.png
          archiveHeight: 144
          archiveWidth: 603
        - name: Merge archive files and save result 
          text: Call Merger class Save method and pass the filename for the resultant archive file as parameter.
          archiveUrl: merger/net/archives/merge-files-step-3.png
          archiveHeight: 151
          archiveWidth: 646
---

## ZIP Merger Python via .NET API

[GroupDocs.Merger](https://products.groupdocs.com/merger/python-net) allows developers to combine multiple archive documents in the preferred order and save them as a single ZIP file.

## About ZIP File Format

A file with .zip extension is an archive that can hold one or more files or directories. The archive can have compression applied to the included files in order to reduce the ZIP file size. ZIP file format was made public back in February 1989 by Phil Katz for achieving archiving of files and folders. The format was made part of PKZIP utility, created by PKWARE, Inc. Right after the availability of available specifications, many companies made ZIP file format part of their software utilities including Microsoft (since Windows 7), Apple (Mac OS X ) and many others.


### How to merge archives to ZIP file

The following example demonstrates how to merge archives to ZIP file with several lines of Python via .NET code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/) class and pass source archive file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another archive file to merge with [join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join) method. Repeat this step for other archive documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/) class [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged archive file as parameter.

```python
with gm.Merger("c:/sample1.zip") as merger:
    merger.join("c:/sample2.tar")
    merger.join("c:/sample3.rar")
    merger.save("c:/merged.zip")
```

### Code Examples

Please find more [use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge Archives Live Demo

GroupDocs.Merger for Python via .NET provides online [**ZIP Merger App**](https://products.groupdocs.app/merger/zip) and [**TAR Merger App**](https://products.groupdocs.app/merger/tar), which allow you to try it for free and check its quality and accuracy.