---
id: rotate-pages
url: merger/python-net/rotate-pages
title: Rotate pages
weight: 8
description: "Following this guide you will learn how to change PDF document page rotation angle using GroupDocs.Merger for Python via .NET API."
keywords: Rotate PDF pages, Rotate document pages, Change PDF page rotation angle
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) allows to change page rotation angle by setting it to 90, 180 or 270 degrees for specific or all document pages.  
Here are the steps to change page rotation:

*   Initialize [RotateOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/RotateOptions) class with desired rotation angle and page numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/net/merger/groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [rotatePages](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/rotatepages/) method and pass [RotateOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/RotateOptions) object to it;
*   Call [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method specifying file path to save resultant document.

The following code sample demonstrates how to change page rotation:

```python
with gm.Merger("c:/sample.pdf") as merger:
    rotate_mode = gm.domain.options.RotateMode.ROTATE180
    rotate_options = gm.domain.options.RotateOptions(rotate_mode, 1, 2)
    merger.rotate_pages(rotate_options)
    merger.save("c:/result.pdf")
```
