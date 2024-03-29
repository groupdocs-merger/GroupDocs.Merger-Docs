---
id: how-to-add-attachment-to-pdf-document
url: merger/java/how-to-add-attachment-to-pdf-document
title: How to add attachment to PDF document
weight: 1
description: "This article explains how to add attachment to PDF document with GroupDocs.Merger within your Java applications."
keywords: add attachment, add attachment to PDF document,  Microsoft Word documents, Excel spreadsheets, PowerPoint presentations, images, audio, video files
productName: GroupDocs.Merger for Java
hideChildren: False
---
It is a known fact PDF files are great for demonstration purposes as your printed content will look the same as it appears on device screen and no formatting will be lost. Another valuable, but less known feature, is that PDF format provides an easy way to organize your documents when you need to store multiple related files alongside. You can just attach other documents like PDF or Microsoft Word documents, Excel spreadsheets, PowerPoint presentations, images, audio or video files to your original PDF document and if you move it to another location, all attachments will move too.

Many desktop tools provide an ability to attach files to a PDF document via their user interfaces, but what if you need to do the same programmatically? Here is where GroupDocs.Merger will come to the rescue.   
Please check the guide below and learn how to add PDF document attachment in 3 steps.

## How to add attachment to PDF document

**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** provides an ability to add PDF document attachment. Here are the steps for it:

*   Instantiate [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) object with source document path or stream;
*   Call [importDocument](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#importDocument(com.groupdocs.merger.domain.options.interfaces.IImportDocumentOptions)) method and pass [PdfAttachmentOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/PdfAttachmentOptions) object to it with a file path to document that is being embedded into PDF;
*   Call [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.lang.String)) method and pass desired file path to save resultant document.

The following code sample demonstrates how to add add PowerPoint presentation attachment to PDF document:

```java
PdfAttachmentOptions olePdfOptions = new PdfAttachmentOptions("c:\presentation-attachment.ppt");

Merger merger = new Merger("c:\sample.pdf");
{
    merger.importDocument(olePdfOptions);
    merger.save("c:\document-with-attachment.pdf");
}
```
