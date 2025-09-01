---
id: split-text-file
url: merger/net/split-text-file
title: Split text file
weight: 5
description: "Follow this guide and learn how to split text file into several resultant files using GroupDocs.Merger for .NET API."
keywords: Split file, Split text file, Split text by line number
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** allows to split text file into several resultant text files. The default behaviour is to split each line into separate file.  
Here are the steps on how to split text file as described:

*   Initialize [TextSplitOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/textsplitoptions) class with output files path format, desired [TextSplitMode](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/textsplitmode) and line numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object with source document path or stream;
*   Call [Split](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/split/#split_1) method and pass [TextSplitOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/textsplitoptions) object to itfor saving resultant text files.

## Split text file to several one-line files (by exact line numbers)

The following code sample demonstrates how to split text file to two one-page documents with 3rd, 6th lines from source file:

```csharp
string filePath = @"c:\sample.txt";
string filePathOut = @"c:\output\line_{0}.{1}";

TextSplitOptions splitOptions = new TextSplitOptions(filePathOut, new int[] { 3, 6 });

using (Merger merger = new Merger(filePath))
{
    merger.Split(splitOptions);
}
```

This code snippet will produce:

| Text file | Line numbers |
| --- | --- |
| line_0 | 3 |
| line_1 | 6 |

## Split text file to several multi-line files 

The following code sample demonstrates how to split text file to several multi-line files starting from 3rd and ending at 6th line numbers:

```csharp
string filePath = @"c:\sample.txt";
string filePathOut = @"c:\output\text_{0}.{1}";

TextSplitOptions splitOptions = new TextSplitOptions(filePathOut, TextSplitMode.Interval, new int[] { 3, 6 });

using (Merger merger = new Merger(filePath))
{
    merger.Split(splitOptions);
}
```

This code snippet will produce:

| Text file | Line numbers |
| --- | --- |
| text_0 | 1, 2 |
| text_1 | 3, 4, 5 |
| text_2 | 6 |

