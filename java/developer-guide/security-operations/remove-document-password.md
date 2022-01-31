---
id: remove-document-password
url: merger/java/remove-document-password
title: Remove document password
weight: 3
description: "This article explains how to remove password for PDF, Word, Excel, PowerPoint documents by using GroupDocs.Merger for Java. "
keywords: Remove document password protection, Remove PDF password, Remove Word document password, Remove Excel spreadsheet password, Remove PowerPoint presentation password
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to remove password from password-protected document.  
Here are the steps to remove document password:

*   Initialize [LoadOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/LoadOptions) class specifying current password;
*   Instantiate [Merger](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream and pass [LoadOptions](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/LoadOptions) object to it;
*   Call [removePassword](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#removePassword()) method;
*   Call [save](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to remove document password:

```java
String filePath = "c:\sample.docx";
String filePathOut = "c:\output\result.docx";

LoadOptions loadOptions = new LoadOptions("SAMPLE_PASSWORD");

Merger merger = new Merger(filePath, loadOptions);        
merger.removePassword();
merger.save(filePathOut);
```
