---
id: add-document-to-spreadsheet-via-ole
url: merger/java/add-document-to-spreadsheet-via-ole
title: Add document to Spreadsheet via OLE
weight: 4
description: "This article explains how to add document to Spreadsheet via OLE with GroupDocs.Merger within your .Java applications."
keywords: add document to Spreadsheet, add document
productName: GroupDocs.Merger for Java
hideChildren: False
---
## What is OLE object for Spreadsheet?

The OLE technology provided by Microsoft allows to insert some other document content into the cell that is previosly selected by RowIndex and ColumnIndex of the currently editing Excel spreadsheet. For example, the PDF document can be inserted in the Excel spreadsheet document as image link inside of predefined cell as was presented in the example below.

## Add document to Spreadsheet via OLE

**[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** provides an ability to add other single document as embedded document to Presentation.   
Here are the steps for it:

*   Initialise [OleSpreadsheetOptions](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/OleSpreadsheetOptions) class with embedded file path and page number;
*   Instantiate [Merger](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger) object with source document path or stream;
*   Call [importDocument](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#importDocument(com.groupdocs.merger.domain.options.interfaces.IImportDocumentOptions)) method and pass [OleSpreadsheetOptions](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/OleSpreadsheetOptions) object to it;
*   Call [save](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#save(java.lang.String)) method and pass desired file path to save resultant document.

The following code sample demonstrates how to add other single document as embedded document to Presentation:

```java
int pageNumber = 2;
OleSpreadsheetOptions oleCellsOptions = new OleSpreadsheetOptions("c:\embedded.pdf", pageNumber);
oleCellsOptions.setRowIndex(2);
oleCellsOptions.setColumnIndex(2);

Merger merger = new Merger("c:\sample.xlsx");
{
    merger.importDocument(oleCellsOptions);
    merger.save("c:\output\result.xlsx");
}

```
