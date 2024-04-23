---
id: how-to-correctly-merge-documents-using-csharp
url: merger/net/getting-started/use-cases/how-to-correctly-merge-documents-using-csharp
title: How to correctly merge documents using C#
description: "This article describes how to correctly merge documents using GroupDocs.Merger for .NET product."
keywords: Merge PDF using file paths in C#, Merge DOCX using file streams in C#, Merge PPTX using memory streams in C#
productName: GroupDocs.Merger for .NET
weight: 11
structuredData:
    productCode: merger
    productPlatform: net
    appName: Merge correctly documents in C#
    appDescription: Merge documents in a quick and efficient way using C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge documents in C# 
        description: Learn how to merge documents in C# language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-c
        steps:
        - name: Load source stream 
          text: Create an instance of Merger class and pass source archive file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other stream
          text: Add other stream you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge documents and save result 
          text: Call Merger class Save method and pass the filename for the resultant archive file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---
# with File Paths

The easiest and most reliable way to merge PDF files, using the "GroupDocs.Merger for .NET" product, is to use the full paths to these files.

The following example demonstrates how to merge PDF files using file paths in C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass the full PDF file path as a constructor parameter.
* Add another PDF file to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged PDF file as parameter.

```csharp
// Load the source PDF file
using (Merger merger = new Merger(@"c:\sample1.pdf"))
{
    // Add another PDF file to merge
    merger.Join(@"c:\sample2.pdf");
    // Merge PDF files and save result
    merger.Save(@"c:\merged.pdf");
}
```

# with File Streams

There are also several ways to work with streams of files that need to be merged using the GroupDocs.Merger product. The most reliable way to combine files without additional parameters is to use the System.FileStream class.

The following example demonstrates how to merge DOCX file streams in C# code:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass the DOCX file stream as a constructor parameter.
* Add another DOCX file stream to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged DOCX file as parameter.

```csharp
string filePath1 = "c:/sample1.docx";
string filePath2 = "c:/sample2.docx";

FileStream fileStream1 = File.OpenRead(filePath1);
FileStream fileStream2 = File.OpenRead(filePath2);

// Load the source DOCX file stream
using (Merger merger = new Merger(fileStream1))
{
    // Add another DOCX file stream to merge
    merger.Join(fileStream2);
    // Merge DOCX file streams and save result
    merger.Save(@"c:\merged.docx");
}
```

# with Memory Streams

There are situations, and quite often, when it is necessary to work with other classes inherited from System.Stream, for example with MemoryStream or others. In this case, it is necessary to use additional parameters to specify the exact file type that is used in this case. Because the "GroupDocs.Merger for .NET" product cannot always accurately determine the file type by its stream. Therefore, to avoid exceptions when merging PDF and other files, see the example below:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass instance of [LoadOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/loadoptions) with PPTX file type as a constructor parameter.
* Create an instance of [JoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/joinoptions) class with PPTX file type as a constructor parameter.
* Add another PPTX stream to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method and pass instance of [JoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/joinoptions) class as a method parameter.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged PPTX file as parameter.

```csharp

string filePath1 = "c:/sample1.pptx";
string filePath2 = "c:/sample2.pptx";

FileType fileType1 = FileType.FromExtension(Path.GetExtension(filePath1));
FileType fileType2 = FileType.FromExtension(Path.GetExtension(filePath2));

MemoryStream memoryStream1 = new MemoryStream();
using (FileStream fileStream1 = File.OpenRead(filePath1))
{
    fileStream1.CopyTo(memoryStream1);
}

MemoryStream memoryStream2 = new MemoryStream();
using (FileStream fileStream2 = File.OpenRead(filePath2))
{
    fileStream2.CopyTo(memoryStream2);
}

// Init Load options with defined FileType
LoadOptions loadOptions = new LoadOptions(fileType1);

// Load the source PPTX stream
using (Merger merger = new Merger(memoryStream1, loadOptions))
{
    // Define join options with PPTX file type
    JoinOptions joinOptions = new JoinOptions(fileType2);
    // Add another PPTX stream to merge
    merger.Join(memoryStream2, joinOptions);
    // Merge PPTX streams and save result
    merger.Save(@"c:\merged.pptx");
}
```

# with Memory Streams for cross-merging

There may also be situations when it is necessary to combine different types of streams into PDF. In this case, you can use the example below:

* Create an instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass instance of [LoadOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/loadoptions) with ini DOCX file type and out PDF one as a constructor parameters.
* Create an instance of [JoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/joinoptions) class with PPTX file type as a constructor parameter.
* Add another PPTX stream to merge with [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method and pass instance of [JoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/joinoptions) class as a method parameter.
* Call [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and specify the filename for the merged PDF file as parameter.

```csharp

string filePath1 = "c:/sample1.docx";
string filePath2 = "c:/sample2.pptx";

MemoryStream memoryStream1 = new MemoryStream();
using (FileStream fileStream1 = File.OpenRead(filePath1))
{
    fileStream1.CopyTo(memoryStream1);
}

MemoryStream memoryStream2 = new MemoryStream();
using (FileStream fileStream2 = File.OpenRead(filePath2))
{
    fileStream2.CopyTo(memoryStream2);
}

// Init Load options with defined FileTypes
LoadOptions loadOptions = new LoadOptions(FileType.DOCX, FileType.PDF);

// Load the source DOCX stream as PDF
using (Merger merger = new Merger(memoryStream1, loadOptions))
{
    // Define join options with PPTX file type
    JoinOptions joinOptions = new JoinOptions(FileType.PPTX);
    // Add another PPTX stream to merge
    merger.Join(memoryStream2, joinOptions);
    // Merge document streams and save PDF result
    merger.Save(@"c:\merged.pdf");
}
```
