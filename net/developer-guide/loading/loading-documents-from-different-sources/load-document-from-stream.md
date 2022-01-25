---
id: load-document-from-stream
url: merger/net/load-document-from-stream
title: Load document from stream
weight: 2
description: "This article explains how to load PDF, Word, Excel, PowerPoint documents from stream when using GroupDocs.Merger for .NET."
keywords: Load document from stream, Load document with GroupDocs.Merger
productName: GroupDocs.Merger for .NET
hideChildren: False
---
There might be the case when source or target document is not physically located on the disk. Instead, you have the document in the form of a stream. In this case, to avoid the overhead of saving stream as a file on disk, **[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** provides a way to work with document streams directly.   
The following are the steps to be followed:
*   Obtain document stream; 
*   Pass opened source document stream to [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class constructor.

Following code snippet describes this case.

```csharp
using (Stream stream = File.OpenRead(@"c:\sample.docx"))
{
	using (Merger merger = new Merger(stream))
    {
    	Console.WriteLine($"Document loaded from stream successfully.");
	}
}
```
