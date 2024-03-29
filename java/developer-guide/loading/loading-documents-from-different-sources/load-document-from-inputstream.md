---
id: load-document-from-inputstream
url: merger/java/load-document-from-inputstream
title: Load document from InputStream
weight: 1
description: "This article explains how to load PDF, Word, Excel, PowerPoint documents from stream when using GroupDocs.Merger for Java."
keywords: Load document from stream, Load document with GroupDocs.Merger
productName: GroupDocs.Merger for Java
hideChildren: False
---
There might be the case when source or target document is not physically located on the disk. Instead, you have the document in the form of a InputStream. In this case, to avoid the overhead of saving InputStream as a file on disk, [**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) provides a way to work with document streams directly.   
The following are the steps to be followed:

*   Obtain document InputStream; 
*   Pass opened source document stream to [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) class constructor.

Following code snippet describes this case.

```java
try {
    InputStream stream = new FileInputStream("c:\\sample.docx");
    Merger merger = new Merger(stream);
    System.out.print("Document loaded from stream successfully.");
} catch (Exception e){
    throw new GroupDocsException(e.getMessage());
}
 
```
