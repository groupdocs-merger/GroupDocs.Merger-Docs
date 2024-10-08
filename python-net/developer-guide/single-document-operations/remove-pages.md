---
id: remove-pages
url: merger/python-net/remove-pages
title: Remove pages
weight: 2
description: "Follow this guide and learn how to remove page from PDF or Word document, delete worksheet from Excel file or remove slides from PowerPoint presentations with GroupDocs.Merger for .NET API."
keywords: Remove page from document, Delete page from document, Remove page, Delete page
productName: GroupDocs.Merger for .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) provides an ability to remove single page or a collection of specific page numbers from the source document.   
Here are the steps to remove document page(s):

*   Initialise [RemoveOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/RemoveOptions) class with page numbers to remove;
*   Instantiate [Merger](https://reference.groupdocs.com/net/merger/groupdocs.merger/Merger) object with source document path or stream;
*   Call [removePages](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/removepages/) method and pass [RemoveOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/RemoveOptions) object to it;
*   Call [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and pass desired file path to save resultant document.

The following code sample demonstrates how to remove document pages:

```python
with gm.Merger("c:/sample.one") as merger:
    remove_options = gm.domain.options.RemoveOptions(1, 2)
    merger.remove_pages(remove_options)
    merger.save("c:/result.one")
```
