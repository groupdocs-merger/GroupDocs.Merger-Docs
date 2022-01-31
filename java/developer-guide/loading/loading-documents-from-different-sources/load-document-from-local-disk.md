---
id: load-document-from-local-disk
url: merger/java/load-document-from-local-disk
title: Load document from local disk
weight: 2
description: "This article explains how to load PDF, Word, Excel, PowerPoint documents from local disk when using GroupDocs.Merger for Java."
keywords: Load document from local disk, Load document from file path, Load document with GroupDocs.Merger
productName: GroupDocs.Merger for Java
hideChildren: False
---
When the source document is located on the local disk [**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows you to load it via [Merger](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) class constructor specifying absolute or relative path to it.  
The following code snippet shows how to load documents from local disk.

```java
String filePath = "c:\sample.docx";
Merger merger = new Merger(filePath);
System.out.print("Document loaded from local disk successfully.");
```
