---
id: add-document-to-diagram-via-ole
url: merger/net/add-document-to-diagram-via-ole
title: Add document to Diagram via OLE
weight: 5
description: "This article explains how to add document to Diagram via OLE with GroupDocs.Merger within your .NET applications."
keywords: add document to Diagram via OLE
productName: GroupDocs.Merger for .NET
hideChildren: False
---
## What is OLE object for Diagram?

The OLE technology provided by Microsoft allows to insert some other document content into the shape with size and coordinates which are previosly selected by X, Y, Width and Height of the currently editing Diagram page. For example, the Slides document can be inserted in the Diagram document inside of shape as was presented in the example below.

## Add document to Diagram via OLE

**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** provides an ability to add other single document as embedded document to Presentation.   
Here are the steps for it:

*   Initialise [OleDiagramOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/olediagramoptions) class with embedded file path and page number;
*   Instantiate [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) object with source document path or stream;
*   Call [ImportDocument](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger/methods/importdocument) method and pass [OleDiagramOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/olediagramoptions) object to it;
*   Call [Save](https://apireference.groupdocs.com/net/merger/groupdocs.merger.merger/save/methods/1) method and pass desired file path to save resultant document.

The following code sample demonstrates how to add other single document as embedded document to Diagram page:

```csharp
string filePath = @"c:\sample.vsdx";
string filePathEmbedded = @"c:\embedded.pptx";
string filePathOut = @"c:\output\result.vsdx";

int pageNumber = 2;
OleDiagramOptions oleDiagramOptions = new OleDiagramOptions(filePathEmbedded, pageNumber);
oleDiagramOptions.X = 1;
oleDiagramOptions.Y = 1;
oleDiagramOptions.Width = 2;
oleDiagramOptions.Height = 1;

using (Merger merger = new Merger(filePath))
{
    merger.ImportDocument(oleDiagramOptions);
    merger.Save(filePathOut);
}

```
