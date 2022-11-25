---
id: add-document-to-word-processing-via-ole
url: merger/java/add-document-to-word-processing-via-ole
title: Add document to Word processing via OLE
weight: 2
description: "This article explains how to add document to Word processing via OLE with GroupDocs.Merger within your Java applications."
keywords: Word processing via OLE, Object Linking and Embedding, PowerPoint presentation
productName: GroupDocs.Merger for Java
hideChildren: False
---
## What is OLE object?

OLE is an abbreviation for "Object Linking and Embedding" technology that is provided by Microsoft and allows to import and embed some content produced by another application into currently edited documents. For example Excel spreadsheet  or PowerPoint presentation can be embedded into documents edited in a word processor and so on. This way OLE allows to store all document related data inside a single document and share this data easily.

## How to add OLE object to Microsoft Word documents

**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** provides an ability to insert OLE objects into word processing documents of Microsoft Word and Open Document formats. Here is how to do this in a 3 easy steps:

*   Instantiate [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) object with source document path or stream;
*   Call [importDocument](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#importDocument(com.groupdocs.merger.domain.options.interfaces.IImportDocumentOptions)) method and pass [OleWordProcessingOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/OleWordProcessingOptions) object with embedded file path and page number;
*   Call [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.lang.String)) method and pass desired file path to save resultant document.

The following code sample demonstrates how to embed PDF file into DOCX document as OLE object

```java
int pageNumber = 2;
OleWordProcessingOptions oleWordsOptions = new OleWordProcessingOptions("c:\embedded.pdf", pageNumber);
oleWordsOptions.setWidth(300);
oleWordsOptions.setHeight(300);

Merger merger = new Merger("c:\sample.docx");

merger.importDocument(oleWordsOptions);
merger.save("c:\output\result.docx");

```
