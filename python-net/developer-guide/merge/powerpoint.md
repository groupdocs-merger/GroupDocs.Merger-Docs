---
id: merge-powerpoint
url: merger/python-net/merge/powerpoint
title: Merge PowerPoint Presentations
weight: 3
description: "This article demonstrates how to merge PowerPoint presentation files of PPT, PPTX, ODP and may other formats with couple net code lines and GroupDocs.Merger for Python via .NET."
keywords: Merge Presentations, Merge PPT files, Merge PPTX files
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge PPSX files in Python via .NET
    appDescription: Merge PPSX in a quick and efficient way using net language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PPSX files in Python via .NET 
        description: Learn how to merge PPSX files in net language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source PPSX files 
          text: Create an instance of Merger class and pass source PPSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other PPSX files
          text: Add other PPSX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PPSX files and save result 
          text: Call Merger class Save method and pass the filename for the resultant PPSX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

You must be familiar with **PPTX** and **PPT** extension files, these are Presentation file formats that store collection of records to accommodate presentation data such as: slides, shapes, text, animations, video, audio and embedded objects. A presentation can be saved/converted into other file formats as well such as PDF, BMP, PNG, JPEG, and XPS.

Common Presentation file extensions and their associated file formats include **PPTX**, **PPT**, **PPSX** and **PPS**.

## How to merge PPSX presentations

PPSX, Power Point Slide Show, file are created using Microsoft PowerPoint 2007 and above for Slide Show purpose. It is an update to the PPS file format that was supported by Microsoft PowerPoint 97-2003 versions. When a PPSX file is shared with another user and opened, it starts as PowerPoint show unlike PPTX file that opens in editable mode. The sequence of slide show is the same as in the original presentation. All the slides accompany the images, sounds and other embedded media accompany the presentation slides to the PPSX during the slideshow.

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class and pass source PPSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another PPSX file to merge with [join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join) method. Repeat this step for other PPSX documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/Merger) class [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged PPSX file as parameter.

```python
with gm.Merger("c:/sample1.ppsx") as merger:
    merger.join("c:/sample2.ppsx")
    merger.save("c:/merged.ppsx")
```

### Code Examples

Please find more [use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge PowerPoint Live Demo

GroupDocs.Merger for Python via .NET provides an online [**PowerPoint Merger App**](https://products.groupdocs.app/merger/powerpoint), which allows you to try it for free and check its quality and accuracy.
