---
id: move-page
url: merger/python-net/move-page
title: Move page
weight: 1
description: "This article demonstrates how to move document page to another position within PDF, Word, Excel, PowerPoint document using GroupDocs.Merger for Python via .NET API."
keywords: Move document page, Move PDF page, Move Word document page, Move page to another position
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
---
[**GroupDocs.Merger**](https://products.groupdocs.com/merger/python-net) provides a move page feature which allows you to manipulate page ordering by moving any page(s) to new position within a document.   
This can be done by following the steps below:

*   Initialise [MoveOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/MoveOptions) class and specify current and new page numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/net/merger/groupdocs.merger/Merger) object with source document path or InputStream;
*   Call [movePage](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/movepage/) method and pass [MoveOptions](https://reference.groupdocs.com/net/merger/groupdocs.merger.domain.options/MoveOptions) object to it;
*   Call [save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and pass desired file path to save resultant document.

The following code sample demonstrates on how to move page to a new position:

```python
with gm.Merger("c:/sample.xlsx") as merger:
    move_options = gm.domain.options.MoveOptions(2, 1)
    merger.move_page(move_options)
    merger.save("c:/result.xlsx")
```
