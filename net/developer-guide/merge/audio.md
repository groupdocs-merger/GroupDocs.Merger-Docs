---
id: merge-audio
url: merger/net/merge/audio
title: Merge audio
description: "Learn how to merge audio files, combine audio files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge audio files in C#, Combine audio files programmatically
productName: GroupDocs.Merger for .NET
toc: True
weight: 50
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge audio files in C#
    appDescription: Merge audio in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Audacity or MP3 Joiner.
    howTo:
        name: How to merge audio files in C# 
        description: Learn how to merge audio files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Audacity or MP3 Joiner.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source audio file
          text: Create an instance of the Merger class and pass the file path of the source audio file as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other audio files
          text: Add other audio files you want to merge into a single file with the Join method of the Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge audio files and save the result 
          text: Call the Save method of the Merger class and pass the filename for the resultant audio file as a parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

## How to merge audio files in C\#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) facilitates developers to combine multiple audio files according to their preferred sequence and save them as a single audio file. This eliminates the need for manual operations with desktop software, saving you valuable time. Currently, GroupDocs.Merger allows combining audio files having the same extensions. For example, WAV file with other WAV files, or MP3 file with other MP3 files.

Here's a C# code snippet demonstrating how to concatenate audio files:

* Create an instance of the [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass the source audio file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements.
* Add another audio file to merge with the [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method. Audio file should be of the same format as the initial one. Repeat this step for other audio files you want to merge.
* Call the [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the resulting audio file as a parameter.

```csharp
// Load the source WAV file
using (var merger = new GroupDocs.Merger.Merger(@"c:\sample1.wav"))
{
    // Add another WAV file to merge
    merger.Join(@"c:\sample2.wav");
    // Merge audio files and save result
    merger.Save(@"c:\merged.wav");
}
```

### Merging Different Audio File Formats

This section describes how to combine miscellaneous audio file formats using GroupDocs.Merger API. Please look at the articles listed below:

* [How to merge WAV files in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-wav-files-using-csharp.md" >}})
* [How to merge MP3 files in C\#]({{< ref "merger/net/getting-started/use-cases/how-to-merge-mp3-files-using-csharp.md" >}})

### Code Examples

Please visit [Showcases]({{< ref "merger/net/showcases.md" >}}) to learn and try our free backend and frontend examples and use-cases!

### Live Demos

GroupDocs.Merger for .NET offers the following free online tools to test its quality and accuracy:
* [**WAV Merger App**](https://products.groupdocs.app/merger/wav)
* [**MP3 Merger App**](https://products.groupdocs.app/merger/mp3)