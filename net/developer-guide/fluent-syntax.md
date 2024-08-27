---
id: fluent-syntax
url: merger/net/fluent-syntax
title: Fluent syntax
weight: 6
description: "Following this guide you will learn how to use fluent syntax of GroupDocs.Merger for .NET API."
keywords: Merger fluent syntax
productName: GroupDocs.Merger for .NET
hideChildren: False
---
Fluent syntax provides a compact call for most public methods of **[GroupDocs.Merger](https://products.groupdocs.com/merger/net)**.

These methods include:
* Join two or more documents,
* Join a specific or group of pages from various documents,
* Split a document into several resultant documents,
* Split document by providing specific page numbers,
* Change page position within a document,
* Remove single or multiple pages from the document,
* Rotate the page to an angle of 90, 180, or 270 degrees,
* Swap the position of two pages within a document,
* Extract a specific page or a range of pages from the document,
* Change page orientation (portrait, landscape) of specific or all pages within a document,
* Set, update or remove the document password,
* etc.
  
Please see the example how to use the fluent syntax below:

```csharp
using (Merger merger = new Merger(@"c:\document1.pdf"))
{
    merger
    .Join(@"c:\document2.docx")
    .Join(@"c:\document3.pptx")
    .Join(@"c:\document4.xlsx")
    .Save(@"c:\merged.pdf");
}
```

