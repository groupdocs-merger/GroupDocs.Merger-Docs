---
id: how-to-merge-wav-files-using-csharp
url: merger/net/getting-started/use-cases/how-to-merge-wav-files-using-csharp
title: How to merge WAV files using C#
description: "Learn how to merge WAV audio files, combine WAV audio files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge WAV audio files in C#, Combine WAV audio files programmatically, Join WAV audio files in C#, Combine WAV audio files in C#, Concatenate WAV audio files in C#
productName: GroupDocs.Merger for .NET
weight: 8
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge WAV audio files in C#
    appDescription: Merge WAV audio files in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Audacity or WavePad.
    howTo:
        name: How to merge WAV audio files in C# 
        description: Learn how to merge WAV audio files in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Audacity or WavePad.
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

## WAV Merger .NET API

Developers can use [GroupDocs.Merger](https://products.groupdocs.com/merger/net) to concatenate multiple WAV audio files in the desired sequence and save them as a single  file.

## About WAV File Format

The WAV (Waveform Audio File Format) is a popular audio file format that is commonly used for storing uncompressed audio data. The format doesn’t apply any compression to the bitstream and stores the audio recordings with different sampling rates and bitrates. It has been and is one of the standard formats for audio CDs. 

WAV files are widely supported by audio software and hardware devices, making them a versatile choice for audio recording, editing, and playback.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/net) to obtain the API DLLs, MSI installer, or NuGet package:
```shell
PM> Install-Package GroupDocs.Merger
```
### Source Audio Files

<audio controls="controls">
  <source type="audio/wav" src="/merger/net/images/audio/sample1.wav"></source>  
  <p>Your browser does not support the audio element.</p>
</audio>

<audio controls="controls">
  <source type="audio/wav" src="/merger/net/images/audio/sample2.wav"></source>  
  <p>Your browser does not support the audio element.</p>
</audio>

### How To Merge Several WAV Files Into A Single File

The following example demonstrates how to combine multiple audio files with several lines of C# code:

* Create an instance of the [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass the source audio file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements.
* Add another audio file to merge with the [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method. Repeat this step for other audio files you want to merge.
* Call the [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the resulting audio file as a parameter.

```csharp
// Load the source WAV file
using (var merger = new GroupDocs.Merger.Merger(@"c:\sample1.wav"))
{
    // Add another WAV file to merge
    merger.Join(@"c:\sample2.wav");
    // Merge WAV files and save result
    merger.Save(@"c:\merged.wav");
}
```

### Result Of Joining WAV Files

<audio controls="controls">
  <source type="audio/wav" src="/merger/net/images/audio/merged.wav"></source>  
  <p>Your browser does not support the audio element.</p>
</audio>

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Combining WAV Live Demo

GroupDocs.Merger for .NET provides an online [**WAV Merger App**](https://products.groupdocs.app/merger/wav), which allows you to try it for free and check its quality and accuracy.