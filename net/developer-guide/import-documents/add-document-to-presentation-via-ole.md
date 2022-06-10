---
id: add-document-to-presentation-via-ole
url: merger/net/add-document-to-presentation-via-ole
title: Add document to Presentation via OLE
weight: 3
description: "This article explains how to add document to Presentation via OLE with GroupDocs.Merger within your .NET applications."
keywords: add document to Presentation, What is OLE object for Presentation
productName: GroupDocs.Merger for .NET
hideChildren: False
---
## What is OLE object for Presentation?

The "Object Linking and Embedding" technology helps to embed some other document in the currently editing Presentation one. For this case, the frame object is using for the embedded document content. The Word and PDF documents, Excel and Oped Document format spreadsheets and other document types can be embedded in a PowerPoint presentation as frame that is predefined with X and Y coordinates and it's size.

## Add document to Presentation via OLE

**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** provides an ability to add other single document as embedded document to Presentation.   
Here are the steps for it:

*   Initialise [OlePresentationOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/olepresentationoptions) class with embedded file path and page number;
*   Instantiate [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) object with source document path or stream;
*   Call [ImportDocument](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger/methods/importdocument) method and pass [OlePresentationOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/olepresentationoptions) object to it;
*   Call [Save](https://apireference.groupdocs.com/net/merger/groupdocs.merger.merger/save/methods/1) method and pass desired file path to save resultant document.

The following code sample demonstrates how to add other single document as embedded document to Presentation:

```csharp
string filePath = @"c:\sample.ppt";
string filePathEmbedded = @"c:\embedded.pdf";
string filePathOut = @"c:\output\result.ppt";

int pageNumber = 2;
OlePresentationOptions olePresentationOptions = new OlePresentationOptions(filePathEmbedded, pageNumber);
olePresentationOptions.X = 10;
olePresentationOptions.Y = 10;

using (Merger merger = new Merger(filePath))
{
    merger.ImportDocument(olePresentationOptions);
    merger.Save(filePathOut);
}

```
