---
id: merge-txt
url: merger/net/merge/txt
title: Merge text files
description: "Learn how to merge TXT files, combine TXT files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge TXT files in C#, Combine TXT files programmatically
productName: GroupDocs.Merger for .NET
weight: 70
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge TXT files in C#
    appDescription: Merge TXT in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge TXT files in C# 
        description: Learn how to merge TXT files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source TXT files 
          text: Create an instance of Merger class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other TXT files
          text: Add other TXT files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge TXT files and save result 
          text: Call Merger class Save method and pass the filename for the resultant TXT file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

## How to merge text files in C\#

When it's required to organize several text files into one file it's possible to solve the task with help of [GroupDocs.Merger](https://products.groupdocs.com/merger/net) only and no need to use any third-party software.

The workflow of combining files together is quite simple:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another TXT file to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method. Repeat this step for other TXT documents you want to merge.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged TXT file as parameter.

The following example demonstrates how to merge TXT files with several lines of C# code:

```csharp
// Load the source TXT file
using (Merger merger = new Merger(@"c:\sample1.txt"))
{
    // Add another TXT file to merge
    merger.Join(@"c:\sample2.txt");
    // Merge TXT files and save result
    merger.Save(@"c:\merged.txt");
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge TXT Live Demo

GroupDocs.Merger for .NET provides an online [**TXT Merger App**](https://products.groupdocs.app/merger/txt), which allows you to try it for free and check its quality and accuracy.
