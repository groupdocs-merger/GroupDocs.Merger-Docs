---
id: split-document
url: merger/java/split-document
title: Split document
weight: 3
description: "This guide describes how to split document of PDF, Word, Excel, PowerPoint and many other formats into several resultant documents using GroupDocs.Merger for Java API."
keywords: Split document, Split PDF, Split Word, Split DOC, Split Presentation, Split Excel
productName: GroupDocs.Merger for Java
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/java) allows to split source document into several resultant documents. Document splitting can be performed in different ways by specifying page numbers array or start/end page numbers and setting different [SplitOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/splitoptions/) modes.  
Here are the possible use cases:

1.  **Page numbers array** specified and splitting mode is set to [SplitMode.Pages](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/splitmode/#Pages) - specified page numbers indicate exact page numbers, which will be saved to the separate one-page documents.  
    *Ex:* Array{ 3, 6, 8 } will produce 3 documents with 3rd, 6th and 8th pages.    
	
2.  **Page numbers array** specified and splitting mode is set to [SplitMode.Interval](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/splitmode/#Interval) - specified page numbers indicate the boundaries of the page intervals, which will be saved to the separate multi-page documents.  
    *Ex:* Array{ 3, 6, 8 } will produce 4 page intervals 1-2, 3-5, 6-7, 8-10.  

There is also an ability to set parameter [RangeMode](https://reference.groupdocs.com/java/merger/com.groupdocs.merger.domain.options/RangeMode) and obtain only even or odd pages from desired pages range.  
  
The steps to split document to multiple on-page documents are the following:

*   Initialize [SplitOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/splitoptions/) class with output files path format;
*   Instantiate [Merger](https://reference.groupdocs.com/java/merger/com.groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [split](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#split-com.groupdocs.merger.domain.options.interfaces.ISplitOptions-) method and pass [SplitOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/splitoptions/) object to itfor saving resultant documents.

### Split the document to several one-page documents (by exact page numbers)
The following code sample demonstrates how to split document to three one-page documents with 3rd, 6th and 8th pages:

```java
String filePath = "c:\sample.docx";
String filePathOut = "c:\output\document_{0}.{1}";

SplitOptions splitOptions = new SplitOptions(filePathOut, new int[] { 3, 6, 8 });
Merger merger = new Merger(filePath);
merger.split(splitOptions);
```

This code snippet will  produce:

| Document name | Page numbers |
| --- | --- |
| document_0 | 3 |
| document_1 | 6 |
| document_2 | 8 |

### Split the document to several one-page documents (by start/end page numbers)

The following code sample demonstrates how to split document to several one-page documents starting from 3rd and ending at 7th page number:

```java
String filePath = "c:\sample.docx";
String filePathOut = "c:\output\document_{0}.{1}";

SplitOptions splitOptions = new SplitOptions(filePathOut, 3, 7);
Merger merger = new Merger(filePath);
merger.split(splitOptions);   
```

This code snippet will  produce:

| Document name | Page numbers |
| --- | --- |
| document_0 | 3 |
| document_1 | 4 |
| document_2 | 5 |
| document_3 | 6 |
| document_4 | 7 |

### Split the document to several one-page documents (by start/end page numbers and even/odd filter)

The following code sample demonstrates how to split document to several one-page documents for odd pages starting from 3rd and ending at 7th page number:

```java
String filePath = "c:\sample.docx";
String filePathOut = "c:\output\document_{0}.{1}";

SplitOptions splitOptions = new SplitOptions(filePathOut, 3, 7, RangeMode.OddPages);
   
Merger merger = new Merger(filePath);
merger.split(splitOptions);
```

This code snippet will produce:

| Document name | Page numbers |
| --- | --- |
| document_0 | 3 |
| document_1 | 5 |
| document_2 | 7 |

### Split the document to several multi-page documents

The following code sample demonstrates how to split document to several multi-page documents:

```java
String filePath = "c:\sample.docx";
String filePathOut = "c:\output\document_{0}.{1}";

SplitOptions splitOptions = new SplitOptions(filePathOut, new int[] { 3, 6, 8 }, SplitMode.Interval);

Merger merger = new Merger(filePath);
merger.split(splitOptions);
```

This code snippet will produce:

| Document name | Page numbers |
| --- | --- |
| document_0 | 1, 2 |
| document_1 | 3, 4, 5 |
| document_2 | 6, 7 |
| document_3 | 8, 9, 10 |
