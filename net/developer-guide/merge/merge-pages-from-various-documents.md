---
id: merge-pages-from-various-documents
url: merger/net/merge-pages-from-various-documents
title: Merge pages from various documents
weight: 110
description: "This article explains how to merge some pages from different documents into single PDF, DOCX, Excel or PowerPoint document using GroupDocs.Merger for .NET."
keywords: Merge PDF pages into one PDF document, Combine document pages into single document, Merge pages into document using GroupDocs.Merger for .NET
productName: GroupDocs.Merger for .NET
hideChildren: False
---
With **[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** you can combine different pages from multiple source documents into a single document. 

* To merge the entire first document along with specific pages from the second and subsequent documents, you can make use of the [PageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pagejoinoptions/) object, which is explained on this page.
* To merge arbitrary pages from all the source documents, you can use the [PageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/) object, which is explained in detail in the [Merge pages in the arbitrary order]({{< ref "merger/net/developer-guide/merge/merge-pages-in-arbitrary-order.md" >}}) section.

Using the [PageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pagejoinoptions/) object, you can merge the source document with specific document pages from the joined documents into one resultant document by specifying desired page numbers or page ranges. Joined documents should be of the same format.

 Here are the steps to join several document parts:

*   Create a [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object and provide the path or stream of the source file.
*   Create a [PageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pagejoinoptions/) object and specify desired page numbers or page ranges to join.
*   Use the [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join_3) to add another source document. Provide the path or stream of the source file and the [PageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pagejoinoptions) object as parameters. Repeat this step for every joined document part.
*   Save the resulting document by calling the [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method and providing a file path.

The following code sample demonstrates how to join document parts:

```csharp
string filePath = @"c:\sample.docx";
string filePath2 = @"c:\sample2.docx";
string filePathOut = @"c:\output\result.docx";

PageJoinOptions joinOptions = new PageJoinOptions(1, 4, RangeMode.OddPages);

using (Merger merger = new Merger(filePath))
{
    merger.Join(filePath2, joinOptions);
    merger.Save(filePathOut);
}
```
