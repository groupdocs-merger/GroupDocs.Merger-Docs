---
id: add-document-to-diagram-via-ole
url: merger/java/add-document-to-diagram-via-ole
title: Add document to Diagram via OLE
weight: 5
description: "This article explains how to add document to Diagram via OLE with GroupDocs.Merger within your Java applications."
keywords: add document to Diagram via OLE
productName: GroupDocs.Merger for Java
hideChildren: False
---
## What is OLE object for Diagram?

The OLE technology provided by Microsoft allows to insert some other document content into the shape with size and coordinates which are previosly selected by X, Y, Width and Height of the currently editing Diagram page. For example, the Slides document can be inserted in the Diagram document inside of shape as was presented in the example below.

## Add document to Diagram via OLE

**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** provides an ability to add other single document as embedded document to Presentation.   
Here are the steps for it:

*   Initialise [OleDiagramOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/OleDiagramOptions) class with embedded file path and page number;
*   Instantiate [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) object with source document path or stream;
*   Call [importDocument](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#importDocument(com.groupdocs.merger.domain.options.interfaces.IImportDocumentOptions)) method and pass [OleDiagramOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/OleDiagramOptions) object to it;
*   Call [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.io.OutputStream)) method and pass desired file path to save resultant document.

The following code sample demonstrates how to add other single document as embedded document to Diagram page:

```csharp
String filePath = "c:\sample.vsdx";
String filePathEmbedded = "c:\embedded.pptx";
String filePathOut = "c:\output\result.vsdx";

int pageNumber = 2;
OleDiagramOptions oleDiagramOptions = new OleDiagramOptions(embeddedFilePath, pageNumber);
oleDiagramOptions.setX(1);
oleDiagramOptions.setY(1);
oleDiagramOptions.setWidth(2);
oleDiagramOptions.setHeight(1);

Merger merger = new Merger(filePath);

merger.importDocument(oleDiagramOptions);
merger.save(filePathOut);

```
