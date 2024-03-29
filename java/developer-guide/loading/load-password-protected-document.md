---
id: load-password-protected-document
url: merger/java/load-password-protected-document
title: Load password-protected document
weight: 2
description: "This article explains how to load password-protected PDF, Word, Excel, PowerPoint documents when using GroupDocs.Merger for Java."
keywords: Load password-protected document, Load protected document with GroupDocs.Merger
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to manipulate with documents that are protected with a password.

The following are the steps to load password-protected documents.

*   Instantiate [LoadOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/LoadOptions) object and specify source document password;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream and [LoadOptions](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/LoadOptions) object created at previous step.

The following code sample shows how to load password-protected documents.

```java
String filePath = "c:\sample.docx";
LoadOptions loadOptions = new LoadOptions("SAMPLE_PASSWORD");
 
Merger merger = new Merger(filePath, loadOptions);
System.out.print("Document loaded successfully.");
```
