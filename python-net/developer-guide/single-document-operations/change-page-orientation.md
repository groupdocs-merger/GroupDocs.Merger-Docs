---
id: change-page-orientation
url: merger/python-net/change-page-orientation
title: Change page orientation
weight: 7
description: "Following this guide you will learn how to change Word document page orientation to Portrait or Landscape using GroupDocs.Merger for Python via .NET."
keywords: DOCX page orientation, Change Word page orientation, Page Portrait orientation, Page Landscape orientation
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) allows to set **Portrait** or **Landscape** page orientation for specific or all document pages.

Here are the steps to change page orientation:

*   Initialize [OrientationOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/OrientationOptions) class with desired orientation mode and page numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/net/merger/groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [changeOrientation](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/changeorientation/) method and pass [OrientationOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/OrientationOptions) object to it;
*   Call [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method specifying file path to save resultant document.

The following code sample demonstrates how to change page orientation:

```python
with gm.Merger("c:/sample1.docx") as merger:
    orientation_mode = gm.domain.options.OrientationMode.LANDSCAPE
    orientation_options = gm.domain.options.OrientationOptions(orientation_mode, 1, 2)
    merger.change_orientation(orientation_options)
    merger.save("c:/merged.docx")
```
