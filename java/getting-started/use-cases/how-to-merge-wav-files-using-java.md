---
id: how-to-merge-wav-files-using-java
url: merger/java/getting-started/use-cases/how-to-merge-wav-files-using-java
title: How to merge WAV files using Java
description: "Learn how to merge WAV audio files, combine WAV audio files into one file programmatically in Java language using GroupDocs.Merger for Java library."
keywords: Merge WAV audio files in Java, Combine WAV audio files programmatically, Join WAV audio files in Java, Combine WAV audio files in Java, Concatenate WAV audio files in Java
productName: GroupDocs.Merger for Java
weight: 10
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge WAV audio files in Java
    appDescription: Merge WAV audio files in a quick and efficient way using Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Audacity or WavePad.
    howTo:
        name: How to merge WAV audio files in Java 
        description: Learn how to merge WAV audio files in Java language and GroupDocs.Merger for Java API, without the use of any third-party software like Audacity or WavePad.
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

## WAV Merger Java API

Developers can use [GroupDocs.Merger](https://products.groupdocs.com/merger/java) to concatenate multiple WAV audio files in the desired sequence and save them as a single  file.

## About WAV File Format

The WAV (Waveform Audio File Format) is a popular audio file format that is commonly used for storing uncompressed audio data. The format doesn’t apply any compression to the bitstream and stores the audio recordings with different sampling rates and bitrates. It has been and is one of the standard formats for audio CDs. 

WAV files are widely supported by audio software and hardware devices, making them a versatile choice for audio recording, editing, and playback.

### Download and Configure

Use the [downloads section](https://downloads.groupdocs.com/merger/java) to obtain the .jar package

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

The following example demonstrates how to combine multiple audio files with several lines of Java code:

* Create an instance of the [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) class and pass the source audio file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements.
* Add another audio file to merge with the [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) method. Repeat this step for other audio files you want to merge.
* Call the [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and specify the filename for the resulting audio file as a parameter.

```java
// Load the source WAV file
Merger merger = new Merger("c:\sample1.wav"))
{
    // Add another WAV file to merge
    merger.join("c:\sample2.wav");
    // Merge WAV files and save result
    merger.save("c:\merged.wav");
}
```

### Result Of Joining WAV Files

<audio controls="controls">
  <source type="audio/wav" src="/merger/net/images/audio/merged.wav"></source>  
  <p>Your browser does not support the audio element.</p>
</audio>

### Code Examples

Please find more [use-cases and complete Java sources]({{< ref "merger/net/showcases.md" >}}) of our backend and frontend examples and try them for free!

### Combining WAV Live Demo

GroupDocs.Merger for .NET provides an online [**WAV Merger App**](https://products.groupdocs.app/merger/wav), which allows you to try it for free and check its quality and accuracy.