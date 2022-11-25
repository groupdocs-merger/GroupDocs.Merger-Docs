---
id: add-document-password
url: merger/java/add-document-password
title: Add document password
weight: 1
description: "This article explains how to add document password for PDF, Word, Excel, PowerPoint and  other file types using GroupDocs.Merger for Java."
keywords: Add document password, Add PDF password, Add Word password, Add Excel password, Add PowerPoint password
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to add document password. Here are the steps to add document password:

*   Initialize [AddPasswordOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/AddPasswordOptions) class with new document password;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [addPassword](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#addPassword(com.groupdocs.merger.domain.options.interfaces.IAddPasswordOptions)) method and pass [AddPasswordOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/AddPasswordOptions) object to it;
*   Call [save](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger#save(java.lang.String)) method specifying file path to save resultant document.

The following code sample demonstrates how to add document password.

```java
String filePath = "c:\sample.pptx";
String filePathOut = "c:\output\result.pptx";

AddPasswordOptions addOptions = new AddPasswordOptions("SAMPLE_PASSWORD");

Merger merger = new Merger(filePath);        
merger.addPassword(addOptions);
merger.save(filePathOut);
```
