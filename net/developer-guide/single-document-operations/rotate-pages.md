---
id: rotate-pages
url: merger/net/rotate-pages
title: Rotate pages
weight: 9
description: "Following this guide you will learn how to change PDF document page rotation angle using GroupDocs.Merger for .NET API."
keywords: Rotate PDF pages, Rotate document pages, Change PDF page rotation angle 
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** allows to change page rotation angle by setting it to 90, 180 or 270 degrees for specific or all document pages.  
Here are the steps to change page rotation:

*   Initialize [RotateOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/rotateoptions) class with desired rotation angle and page numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object with source document path or stream;
*   Call [RotatePages](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/rotatepages) method and pass [RotateOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/rotateoptions) object to it;
*   Call [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method specifying file path to save resultant document.

The following code sample demonstrates how to change page rotation:

```csharp
string filePath = @"c:\sample.pdf";
string filePathOut = @"c:\output\result.pdf";

RotateOptions rotateOptions = new RotateOptions(RotateMode.Rotate180, new int[] { 2, 3, 6 });

using (Merger merger = new Merger(filePath))
{
    merger.RotatePages(rotateOptions);
    merger.Save(filePathOut);
}
```
