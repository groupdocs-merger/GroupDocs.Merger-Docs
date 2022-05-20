---
id: get-supported-file-types
url: merger/net/get-supported-file-types
title: Get supported file types
weight: 1
description: "This article explains how to obtain supported file formats list when merge PDF, Word(DOC, DOCX), Excel(XLS, XLSX), PowerPoint(PPT, PPTX) documents with GroupDocs.Merger within your .NET applications."
keywords: Word, DOC, DOCX, Excel, XLS, XLSX, PowerPoint, PPT, PPTX
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** allows to get the list of all [supported file types]({{< ref "merger/net/getting-started/supported-document-formats.md" >}}) by following the below steps:

*   Call [GetSupportedFileTypes](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain/filetype/methods/getsupportedfiletypes) of [FileType](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain/filetype) class;
*   Enumerate through the collection of [FileType](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain/filetype) objects.

The following code sample demonstrates how to get supported file formats list.

```csharp
IEnumerable<FileType> supportedFileTypes = FileType
	.GetSupportedFileTypes()
	.OrderBy(f => f.Extension);

foreach (FileType fileType in supportedFileTypes)
	Console.WriteLine(fileType);
```
