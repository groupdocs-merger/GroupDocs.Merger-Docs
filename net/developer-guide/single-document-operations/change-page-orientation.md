---
id: change-page-orientation
url: merger/net/change-page-orientation
title: Change page orientation
weight: 7
description: "Following this guide you will learn how to change Word document page orientation to Portrait or Landscape using GroupDocs.Merger for .NET."
keywords: DOCX page orientation, Change Word page orientation, Page Portrait orientation, Page Landscape orientation, 
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** allows to set **Portrait** or **Landscape** page orientation for specific or all document pages.

Here are the steps to change page orientation:

*   Initialize [OrientationOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/orientationoptions) class with desired orientation mode and page numbers;
*   Instantiate [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object with source document path or stream;
*   Call [ChangeOrientation](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/changeorientation) method and pass [OrientationOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/orientationoptions) object to it;
*   Call [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method specifying file path to save resultant document.

The following code sample demonstrates how to change page orientation:

```csharp
string filePath = @"c:\sample.docx";
string filePathOut = @"c:\output\result.docx";

OrientationOptions orientationOptions = new OrientationOptions(OrientationMode.Landscape, new int[] { 3, 4 });

using (Merger merger = new Merger(filePath))
{
    merger.ChangeOrientation(orientationOptions);
    merger.Save(filePathOut);
}
```
