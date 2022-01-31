---
id: load-document-from-url
url: merger/java/load-document-from-url
title: Load document from URL
weight: 3
description: "This article explains how to load PDF, Word, Excel, PowerPoint documents from local disk when using GroupDocs.Merger for Java."
keywords: Load document from local disk, Load document from file path, Load document with GroupDocs.Merger
productName: GroupDocs.Merger for Java
hideChildren: False
---
Following example demonstrates how to load document from URL.

```java
String url = "https://github.com/groupdocs-merger/GroupDocs.Merger-for-Java/blob/master/Examples/Resources/SampleFiles/Pdf/sample.pdf?raw=true";
try {
    InputStream stream = new java.net.URL(url).openStream();

    LoadOptions loadOptions = new LoadOptions(FileType.PDF);
    Merger merger = new Merger(stream, loadOptions);
    System.out.print("Document loaded from URL successfully.");
} catch ( Exception e){
    throw new GroupDocsMergerException(e.getMessage());
}
```
