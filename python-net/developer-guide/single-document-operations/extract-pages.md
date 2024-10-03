---
id: extract-pages
url: merger/python-net/extract-pages
title: Extract pages
weight: 6
description: "Following this guide you will learn how to extract pages from PDF, Word, Excel, PowerPoint and many other file types using GroupDocs.Merger for Python via .NET."
keywords: Extract page from PDF, Extract page from Word, Extract worksheet from Excel, Extract slide from PowerPoint, Extract document pages
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
## Extract pages 

[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) allows to extract pages from source document. The result is a new document that contains only specified pages from the source document.

Here are the steps to extract document pages:

*   Initialize [ExtractOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/ExtractOptions) class with page numbers that should appear in the resultant document;
*   Instantiate [Merger](https://reference.groupdocs.com/net/merger/groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [extractPages](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/extractpages/) method and pass [ExtractOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/ExtractOptions) object to it;
*   Call [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method specifying file path to save resultant document.

The following code sample demonstrates how to extract document pages **by specifying exact page numbers**:

```python
with gm.Merger("c:/sample.pdf") as merger:
    extract_options = gm.domain.options.ExtractOptions(1, 2)
    merger.extract_pages(extract_options)
    merger.save("c:/result.pdf")
```

The following code sample demonstrates how to extract document pages **by specifying page numbers range**:

```python
with gm.Merger("c:/sample.pdf") as merger:
    even_pages = gm.domain.options.RangeMode.EVENPAGES
    extract_options = gm.domain.options.ExtractOptions(1, 3, even_pages)
    merger.extract_pages(extract_options)
    merger.save("c:/result.pdf")
```
