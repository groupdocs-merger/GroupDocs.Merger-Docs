---
id: add-document-to-word-processing-via-ole
url: merger/net/add-document-to-word-processing-via-ole
title: Add document to Word processing via OLE
weight: 2
description: "This article explains how to add document to Word processing via OLE with GroupDocs.Merger within your .NET applications."
keywords: Word processing via OLE, Object Linking and Embedding, PowerPoint presentation
productName: GroupDocs.Merger for .NET
hideChildren: False
---
## What is OLE object?

OLE is an abbreviation for "Object Linking and Embedding" technology that is provided by Microsoft and allows to import and embed some content produced by another application into currently edited documents. For example Excel spreadsheet  or PowerPoint presentation can be embedded into documents edited in a word processor and so on. This way OLE allows to store all document related data inside a single document and share this data easily.

## How to add OLE object to Microsoft Word documents

**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** provides an ability to insert OLE objects into word processing documents of Microsoft Word and Open Document formats. Here is how to do this in a 3 easy steps:

*   Instantiate [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object with source document path or stream;
*   Call [ImportDocument](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/importdocument) method and pass [OleWordProcessingOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/olewordprocessingoptions) object with embedded file path and page number;
*   Call [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method and pass desired file path to save resultant document.

The following code sample demonstrates how to embed PDF file into DOCX document as OLE object

```csharp
using (Merger merger = new Merger(@"c:\sample.docx"))
{
	int pageNumber = 2;
	OleWordProcessingOptions oleWordProcessingOptions = new OleWordProcessingOptions(@"c:\embedded.pdf", pageNumber);
	oleWordProcessingOptions.Width = 300;
	oleWordProcessingOptions.Height = 300;

    merger.ImportDocument(oleWordProcessingOptions);
    merger.Save(@"c:\output\result.docx");
}

```
