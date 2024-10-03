---
id: split-document
url: merger/python-net/split-document
title: Split document
weight: 3
description: "This guide describes how to split document of PDF, Word, Excel, PowerPoint and many other formats into several resultant documents using GroupDocs.Merger for Python via .NET API."
keywords: Split document, Split PDF, Split Word, Split DOC, Split Presentation, Split Excel
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) allows to split source document into several resultant documents. Document splitting can be performed in different ways by specifying page numbers array or start/end page numbers and setting different [SplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/splitoptions/) modes.  
Here are the possible use cases:

1.  **Page numbers array** specified and splitting mode is set to [SplitMode.Pages](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/splitmode/) - specified page numbers indicate exact page numbers, which will be saved to the separate one-page documents.  
    *Ex:* Array{ 3, 6, 8 } will produce 3 documents with 3rd, 6th and 8th pages.    
	
2.  **Page numbers array** specified and splitting mode is set to [SplitMode.Interval](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/splitmode/) - specified page numbers indicate the boundaries of the page intervals, which will be saved to the separate multi-page documents.  
    *Ex:* Array{ 3, 6, 8 } will produce 4 page intervals 1-2, 3-5, 6-7, 8-10.  

There is also an ability to set parameter [RangeMode](https://reference.groupdocs.com/python-net/merger/groupdocs.merger.domain.options/RangeMode) and obtain only even or odd pages from desired pages range.  
  
The steps to split document to multiple on-page documents are the following:

*   Initialize [SplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/splitoptions/) class with output files path format;
*   Instantiate [Merger](https://reference.groupdocs.com/python-net/merger/groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [split](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/splitoptions/) method and pass [SplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/splitoptions/) object to itfor saving resultant documents.

### Split the document to several one-page documents (by exact page numbers)
The following code sample demonstrates how to split document to three one-page documents with 3rd, 6th and 8th pages:

```python
with gm.Merger("c:/sample.docx") as merger:
    output_path = "c:/output/document_{0}.{1}"
    split_options = gm.domain.options.SplitOptions(output_path, [3, 6, 8])
    merger.split(split_options)
```

This code snippet will  produce:

| Document name | Page numbers |
| --- | --- |
| document_0 | 3 |
| document_1 | 6 |
| document_2 | 8 |

### Split the document to several one-page documents (by start/end page numbers)

The following code sample demonstrates how to split document to several one-page documents starting from 3rd and ending at 7th page number:

```python
with gm.Merger("c:/sample.docx") as merger:
    output_path = "c:/output/document_{0}.{1}"
    split_options = gm.domain.options.SplitOptions(output_path, 3, 7)
    merger.split(split_options)
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

```python
with gm.Merger("c:/sample.docx") as merger:
    output_path = "c:/output/document_{0}.{1}"
    range_mode = gm.domain.options.RangeMode.ODDPAGES;
    split_options = gm.domain.options.SplitOptions(output_path, 3, 7, range_mode)
    merger.split(split_options)
```

This code snippet will produce:

| Document name | Page numbers |
| --- | --- |
| document_0 | 3 |
| document_1 | 5 |
| document_2 | 7 |

### Split the document to several multi-page documents

The following code sample demonstrates how to split document to several multi-page documents:

```python
with gm.Merger("c:/sample.docx") as merger:
    output_path = "c:/output/document_{0}.{1}"
    split_mode = gm.domain.options.SplitMode.INTERVAL;
    split_options = gm.domain.options.SplitOptions(output_path, [3, 6, 8], split_mode)
    merger.split(split_options)
```

This code snippet will produce:

| Document name | Page numbers |
| --- | --- |
| document_0 | 1, 2 |
| document_1 | 3, 4, 5 |
| document_2 | 6, 7 |
| document_3 | 8, 9, 10 |
