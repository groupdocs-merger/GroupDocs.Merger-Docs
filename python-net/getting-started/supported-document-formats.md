---
id: supported-document-formats
url: merger/python-net/supported-document-formats
title: Get supported document formats
weight: 1
description: "This article explains how to obtain supported file formats list when merge PDF, Word(DOC, DOCX), Excel(XLS, XLSX), PowerPoint(PPT, PPTX) documents with GroupDocs.Merger within your Python via .NET applications."
keywords: Word, DOC, DOCX, Excel, XLS, XLSX, PowerPoint, PPT, PPTX
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) allows to get the list of all [supported file types]({{< ref "merger/python-net/getting-started/supported-document-formats.md" >}}) by following the below steps:
*   Call [getSupportedFileTypes](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain/filetype/getsupportedfiletypes/) method of [FileType](https://reference.groupdocs.com/python-net/merger/groupdocs.merger.domain/FileType) class;
*   Enumerate through the collection of [FileType](https://reference.groupdocs.com/python-net/merger/groupdocs.merger.domain/FileType) objects.

The following code sample demonstrates how to get supported file formats list.

```python
supported_file_types = gm.domain.FileType.get_supported_file_types()
    for supported_file_type in supported_file_types:
        print(f"Property value: {supported_file_type.extension}")
```
