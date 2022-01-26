---
id: merge-html
url: merger/net/merge/html
title: Merge HTML
description: "Learn how to merge HTML files, combine HTML files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge HTML files in C#, Combine HTML files programmatically
productName: GroupDocs.Merger for .NET
weight: 1
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge HTML files in C#
    appDescription: Merge HTML in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge HTML files in C# 
        description: Learn how to merge HTML files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source HTML files 
          text: Create an instance of Merger class and pass source HTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other HTML files
          text: Add other HTML files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge HTML files and save result 
          text: Call Merger class Save method and pass the filename for the resultant HTML file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

HTML (Hyper Text Markup Language) is the extension for web pages created for display in browsers. Known as language of the web, HTML has evolved with requirements of new information requirements to be displayed as part of web pages. The latest variant is known as HTML 5 that gives a lot of flexibility for working with the language. HTML pages are either received from server, where these are hosted, or can be loaded from local system as well.

## How to merge HTML files programmatically

When you need to merge multiple HTML pages into a single file you can do this  with help of [GroupDocs.Merger](https://products.groupdocs.com/merger/net) and all content like text, images, tables, graphs, forms etc. will be preserved.

The following in an example of how to merge HTML files programmatically:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source HTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another HTML file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other HTML documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged HTML file as parameter.

```csharp
// Load the source HTML file
using (Merger merger = new Merger(@"c:\sample1.html"))
{
    // Add another HTML file to merge
    merger.Join(@"c:\sample2.html");
    // Merge HTML files ans save result
    merger.Save(@"c:\merged.html");
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge HTML Live Demo

GroupDocs.Merger for .NET provides an online [**HTML Merger App**](https://products.groupdocs.app/merger/html), which allows you to try it for free and check its quality and accuracy.
