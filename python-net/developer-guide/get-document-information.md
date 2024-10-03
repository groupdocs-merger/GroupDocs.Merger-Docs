---
id: get-document-information
url: merger/python-net/get-document-information
title: Get document information
weight: 2
description: "This article explains how to detect document file type and calculate pages count when merge PDF, Word(DOC, DOCX), Excel(XLS, XLSX), PowerPoint(PPT, PPTX) files with GroupDocs.Merger for Python via .NET."
keywords: Word, DOC, DOCX, Excel, XLS, XLSX, PowerPoint, PPT, PPTX
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) allows to get document information which includes:

*   [FileType](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.result/idocumentinfo/type/)
*   [PageCount](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.result/idocumentinfo/pagecount/)
*   [Page info ](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.result/IPageInfo)for each document page.

  
The following code sample demonstrates how to get document information.

```python
with gm.Merger("c:/sample.vsdx") as merger:
    info = merger.get_document_info()
```
