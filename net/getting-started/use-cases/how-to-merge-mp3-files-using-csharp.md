---
id: how-to-merge-mp3-files-using-csharp
url: merger/net/getting-started/use-cases/how-to-merge-mp3-files-using-csharp
title: How to merge MP3 files using C#
description: "Learn how to merge MP3 audio files, combine MP3 audio files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge MP3 audio files in C#, Combine MP3 audio files programmatically
productName: GroupDocs.Merger for .NET
weight: 9
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge MP3 audio files in C#
    appDescription: Merge MP3 audio files in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Audacity or MP3 Joiner.
    howTo:
        name: How to merge MP3 audio files in C# 
        description: Learn how to merge MP3 audio files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Audacity or MP3 Joiner.
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

## MP3 Merger .NET API

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to combine multiple MP3 audio files in the preferred order and save them as a single file.

## About MP3 File Format

The MP3 (MPEG-1 Audio Layer 3) file format is a widely used audio compression format known for its ability to significantly reduce the file size of audio recordings while maintaining reasonably good sound quality. MP3 is a lossy audio compression format, which means that it achieves smaller file sizes by removing some of the audio data that is less perceptible to the human ear. 

MP3 is one of the most universally supported audio formats. It is compatible with a wide range of devices, software, and platforms, making it suitable for sharing and playback across different systems.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/net) to obtain the API DLLs, MSI installer, or NuGet package:
```shell
PM> Install-Package GroupDocs.Merger
```

### How to merge several MP3 files into a single file

The following example demonstrates how to merge multiple audio files with several lines of C# code:

* Create an instance of the [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass the source audio file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements.
* Add another audio file to merge with the [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method. Repeat this step for other audio files you want to merge.
* Call the [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the resulting audio file as a parameter.

```csharp
// Load the source MP3 file
using (var merger = new GroupDocs.Merger.Merger(@"c:\sample1.mp3"))
{
    // Add another MP3 file to merge
    merger.Join(@"c:\sample2.mp3");
    // Add next audio file to merge
    merger.Join(@"c:\sample3.mp3");
    // Merge MP3 files and save result
    merger.Save(@"c:\merged.mp3");
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Merge MP3 Live Demo

GroupDocs.Merger for .NET provides an online [**MP3 Merger App**](https://products.groupdocs.app/merger/mp3), which allows you to try it for free and check its quality and accuracy.