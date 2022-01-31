---
id: get-document-information
url: merger/java/get-document-information
title: Get document information
weight: 2
description: "This article explains how to detect document file type and calculate pages count when merge PDF, Word, Excel, PowerPoint files with GroupDocs.Merger for Java."
keywords: 
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to get document information which includes:

*   [FileType](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.result/IDocumentInfo#getType())
*   [PageCount](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.result/IDocumentInfo#getPageCount())
*   [Page info ](https://apireference.groupdocs.com/java/merger/com.groupdocs.merger.domain.result/IPageInfo)for each document page.

  
The following code sample demonstrates how to get document information.

```java
Merger merger = new Merger("c:\sample.vsdx");

IDocumentInfo info = merger.getDocumentInfo();
System.out.print(info);        


```
