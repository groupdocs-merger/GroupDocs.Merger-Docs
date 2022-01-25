---
id: get-document-information
url: merger/net/get-document-information
title: Get document information
weight: 2
description: "This article explains how to detect document file type and calculate pages count when merge PDF, Word, Excel, PowerPoint files with GroupDocs.Merger."
keywords: 
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** allows to get document information which includes:
*   [Type](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.result/documentinfo/properties/type) - indicates document file type, extension, format name etc.
*   [PageCount](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.result/documentinfo/properties/pagecount) - indicates count of pages for text processing document, worksheets in a spreadsheet or slides in a presentation;
*   [Page info](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.result/ipageinfo) - describes properties for each document page. For example, height and width in pixels when document page is previewed as image, page number, visibility etc.

The following code sample demonstrates how to get document information.
```csharp
using (Merger merger = new Merger(@"c:\sample.vsdx"))
{
    IDocumentInfo info = merger.GetDocumentInfo();
    Console.WriteLine(info);
}
```
