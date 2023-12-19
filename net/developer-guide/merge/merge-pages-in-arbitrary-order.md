---
id: merge-pages-in-arbitrary-order
url: merger/net/merge-pages-in-arbitrary-order
title: Merge pages in the arbitrary order
weight: 120
description: "This article explains how to merge arbitrary pages from different documents into a single PDF, DOCX, Excel or PowerPoint document using GroupDocs.Merger for .NET."
keywords: Merge PDF pages into one PDF document, Combine document pages into single document, Merge pages into document using GroupDocs.Merger for .NET
productName: GroupDocs.Merger for .NET
toc: True
hideChildren: False
---
With **[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** you can combine different pages from multiple source documents into a single document. 

* To merge the entire first document along with specific pages from the second and subsequent documents, you can make use of the [PageJoinOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pagejoinoptions/) object, which is explained in detail in the [Merge pages from various documents]({{< ref "merger/net/developer-guide/merge/merge-pages-from-various-documents.md" >}}) section.

* To merge arbitrary pages from all the source documents, you can use the [PageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/) object, which is explained on this page.


Using the [PageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/) object, you can define the specific order in which the pages from the source documents will be combined. For instance, you can merge the 3rd page from Document A with the 5th page from Document B and then with the 2nd page from Document A.

To start using the `PageBuilder` class, you need to create an instance of it. You can then use the `AddPage` method to append a single page, or the `AddPageRange` method to append a range of pages. Once you have added all the pages in the required order, you can apply them to the documents by calling the `Merger.ApplyPageBuilder` method.


## Specifying the required pages by their number

The `AddPage` method allows several ways to define the page to be added.
The easiest way is to pass the `IPageInfo` object that describes the page's source document and its number. 

Here are the steps to combine several pages from various documents specifying the pages by their numbers:

*   Create a [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object and provide the path or stream of the source file.
*   Use the [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join_3) to add another source document. Repeat this step for each document you want to merge.
*   Create a [PageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/) object by calling the `Merger.CreatePageBuilder` method.
*   Call the [AddPage](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/addpage) method and pass the `IPageInfo` object describing the appropriate page. Note that the `IPageInfo` object uses zero-based notation for both source documents and page numbers.  Repeat this step for every page you want to add.
*   Use the [ApplyPageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/applypagebuilder) method to apply the specified order of pages to the merged document.
*   Save the resulting document by calling the [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method and providing a file path.


```csharp
string filePath = @"c:\sample.docx";
string filePath2 = @"c:\sample2.docx";
string filePathOut = @"c:\output\result.docx";

using (Merger merger = new Merger(filePath))
{
    merger.Join(filePath2);

    PageBuilder pageBuilder = merger.CreatePageBuilder();
    // Add page 1 from the first document
    pageBuilder.AddPage(pageBuilder.Documents[0].Pages[0]);
    // Add page 3 from the second document
    pageBuilder.AddPage(pageBuilder.Documents[1].Pages[2]);
    // Add page 4 from the first document 
    pageBuilder.AddPage(pageBuilder.Documents[0].Pages[3]);
    // Add page 2 from the second document
    pageBuilder.AddPage(pageBuilder.Documents[1].Pages[1]);
    // Add page 1 from the second document
    pageBuilder.AddPage(pageBuilder.Documents[1].Pages[0]);
    // Add page 6 from the first document 
    pageBuilder.AddPage(pageBuilder.Documents[0].Pages[5]);

    // Apply the page order
    merger.ApplyPageBuilder(pageBuilder);

    merger.Save(filePathOut);
}
```

## Specifying the required pages by their index

When adding many pages, specifying them by number is not optimal since in that case each call of the `AddPage` method invokes loading of document information. To improve performance, you can skip loading the document information and specify pages by their index instead.

To combine several pages from various documents specifying the pages by their index:

*   Create a [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object and provide the path or stream of the source file.
*   Use the [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join_3) to add another source document. Repeat this step for each document you want to merge.
*   Create a [PageBuilderOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pagebuilderoptions/) object and set the `LoadDocumentInfo` property to `false`.
*   Create a [PageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/) object by calling the `Merger.CreatePageBuilder` method and pass the `PageBuilderOptions` to it.
*   Call the [AddPage](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/addpage) method and pass the source document index and the index number of the needed page. Repeat this step for every page you want to add.
*   Call the [ApplyPageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/applypagebuilder) method to apply the specified order of pages to the merged document.
*   Save the resulting document by calling the [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method and providing a file path.

```csharp
string filePath = @"c:\sample.docx";
string filePath2 = @"c:\sample2.docx";
string filePathOut = @"c:\output\result.docx";

using (Merger merger = new Merger(filePath))
{
    merger.Join(filePath2);

    PageBuilderOptions pageBuilderOptions = new PageBuilderOptions();
    pageBuilderOptions.LoadDocumentInfo = false;

    PageBuilder pageBuilder = merger.CreatePageBuilder(pageBuilderOptions);
    // Add page 1 from the first document
    pageBuilder.AddPage(pageBuilder.Documents[0].Index, 1);
    // Add page 3 from the second document
    pageBuilder.AddPage(pageBuilder.Documents[1].Index, 3);
    // Add page 4 from the first document 
    pageBuilder.AddPage(pageBuilder.Documents[0].Index, 4);
    // Add page 2 from the second document
    pageBuilder.AddPage(pageBuilder.Documents[1].Index, 2);
    // Add page 1 from the second document
    pageBuilder.AddPage(pageBuilder.Documents[1].Index, 1);
    // Add page 6 from the first document 
    pageBuilder.AddPage(pageBuilder.Documents[0].Index, 6);
    
    // Apply the page order
    merger.ApplyPageBuilder(pageBuilder);

    merger.Save(filePathOut);
}
```
## Specifying the range of the required pages

When you need to add multiple pages at once, you can use the `AddPageRange` method. It accepts an array of `IPageInfo` objects, each describing the appropriate page.

Here are the steps to combine several pages from various documents specifying them as a range:

*   Create a [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object and provide the path or stream of the source file.
*   Use the [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join/#join_3) to add another source document. Repeat this step for each document you want to merge.
*   Create a [PageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/) object by calling the `Merger.CreatePageBuilder` method.
*   Call the [AddPageRange](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.builders/pagebuilder/addpagerange) method and pass an array of `IPageInfo` objects describing the appropriate pages. Please note that `IPageInfo` objects use zero-based notation for source documents and page numbers.
*   Use the [ApplyPageBuilder](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/applypagebuilder) method to apply the specified order of pages to the merged document.
*   Save the resulting document by calling the [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method and providing a file path.


```csharp
string filePath = @"c:\sample.docx";
string filePath2 = @"c:\sample2.docx";
string filePathOut = @"c:\output\result.docx";

using (Merger merger = new Merger(filePath))
{
    merger.Join(filePath2);

    PageBuilder pageBuilder = merger.CreatePageBuilder();
    // Specify a range of pages
    IPageInfo range = new IPageInfo[] {
                    pageBuilder.Documents[0].Pages[0], // Page 1 from the first document
                    pageBuilder.Documents[1].Pages[2], // Page 3 from the second document
                    pageBuilder.Documents[0].Pages[3], // Page 4 from the first document
                    pageBuilder.Documents[1].Pages[1], // Page 2 from the second document
                    pageBuilder.Documents[1].Pages[0], // Page 1 from the second document
                    pageBuilder.Documents[0].Pages[5], // Page 6 from the first document                    
                };
    // Append a page of pages
    pageBuilder.AddPageRange(range);

    // Apply the page order
    merger.ApplyPageBuilder(pageBuilder);

    merger.Save(filePathOut);
}
```