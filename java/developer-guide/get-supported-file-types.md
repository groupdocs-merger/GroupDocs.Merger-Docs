---
id: get-supported-file-types
url: merger/java/get-supported-file-types
title: Get supported file types
weight: 1
description: "This article explains how to obtain supported file formats list when merge PDF, Word, Excel, PowerPoint documents with GroupDocs.Merger within your Java applications."
keywords: 
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to get the list of all [supported file types]({{< ref "merger/java/getting-started/supported-document-formats.md" >}}) by following the below steps:
*   Call [getSupportedFileTypes](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain/FileType#getSupportedFileTypes()) method of [FileType](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain/FileType) class;
*   Enumerate through the collection of [FileType](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain/FileType) objects.

The following code sample demonstrates how to get supported file formats list.

```java
List<FileType> fileTypes = FileType.getSupportedFileTypes();

for(FileType fileType : fileTypes)
{
    System.out.print(fileType.getExtension());
}
```
