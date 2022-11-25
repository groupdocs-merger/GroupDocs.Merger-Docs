---
id: update-document-password
url: merger/java/update-document-password
title: Update document password
weight: 4
description: "This article explains how to update password for PDF, Word, Excel, PowerPoint documents by using GroupDocs.Merger for Java."
keywords: Update document password protection, Update PDF password, Update Word document password, Update Excel spreadsheet password, Update PowerPoint password
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to update password from password-protected document. The resultant document will have new password.  
Here are the steps to update document password:

*   Initialize [LoadOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/LoadOptions) class specifying current password;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream and pass [LoadOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/LoadOptions) object to it;
*   Initialize [UpdatePasswordOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/UpdatePasswordOptions) class specifying new document password;
*   Call [updatePassword](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#updatePassword(com.groupdocs.merger.domain.options.interfaces.IUpdatePasswordOptions)) method and pass [UpdatePasswordOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/UpdatePasswordOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to update document password:

```java
String filePath = "c:\sample.xlsx";
String filePathOut = "c:\output\result.xlsx";

ILoadOptions loadOptions = new LoadOptions("SAMPLE_PASSWORD");
IUpdatePasswordOptions updateOptions = new UpdatePasswordOptions("NEW_SAMPLE_PASSWORD");

Merger merger = new Merger(filePath, loadOptions);        
merger.updatePassword(updateOptions);
merger.save(filePathOut);
```
