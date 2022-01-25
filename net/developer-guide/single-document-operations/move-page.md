---
id: move-page
url: merger/net/move-page
title: Move page
weight: 1
description: "This article demonstrates how to move document page to another position within PDF, Word, Excel, PowerPoint document using GroupDocs.Merger API."
keywords: Move document page, Move PDF page, Move Word document page, Move page to another position
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** provides a move page feature which allows you to manipulate page ordering by moving any page(s) to new position within a document.   
This can be done by following the steps below:

*   Initialise [MoveOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/moveoptions) class and specify current and new page numbers;
*   Instantiate [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) object with source document path or stream;
*   Call [MovePage](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger/methods/movepage) method and pass [MoveOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/moveoptions) object to it;
*   Call [Save](https://apireference.groupdocs.com/net/merger/groupdocs.merger.merger/save/methods/1) method and pass desired file path to save resultant document.

The following code sample demonstrates on how to move page to a new position:

```csharp
int pageNumber = 6;
int newPageNumber = 1;
MoveOptions moveOptions = new MoveOptions(pageNumber, newPageNumber);

using (Merger merger = new Merger(@"c:\sample.xlsx"))
{
    merger.MovePage(moveOptions);
    merger.Save(@"c:\result.xlsx");
}
```
