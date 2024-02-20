---
id: merge-pages-in-arbitrary-order
url: merger/java/merge-pages-in-arbitrary-order
title: Merge pages in the arbitrary order
weight: 120
description: "This article explains how to merge arbitrary pages from different documents into a single PDF, DOCX, Excel or PowerPoint document using GroupDocs.Merger for Java."
keywords: Merge PDF pages into one PDF document, Combine document pages into single document, Merge pages into document using GroupDocs.Merger for Java
productName: GroupDocs.Merger for Java
toc: True
hideChildren: False
---
With **[GroupDocs.Merger](https://products.groupdocs.com/merger/java)** you can combine different pages from multiple source documents into a single document. 

* To merge the entire first document along with specific pages from the second and subsequent documents, you can make use of the [PageJoinOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/pagejoinoptions/) object, which is explained in detail in the [Merge pages from various documents]({{< ref "merger/java/developer-guide/merge/merge-pages-from-various-documents.md" >}}) section.

* To merge arbitrary pages from all the source documents, you can use the [PageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/) object, which is explained on this page.


Using the [PageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/) object, you can define the specific order in which the pages from the source documents will be combined. For instance, you can merge the 3rd page from Document A with the 5th page from Document B and then with the 2nd page from Document A.

To start using the `PageBuilder` class, you need to create an instance of it. You can then use the `addPage` method to append a single page, or the `addPageRange` method to append a range of pages. Once you have added all the pages in the required order, you can apply them to the documents by calling the `Merger.applyPageBuilder` method.


## Specifying the required pages by their number

The `addPage` method allows several ways to define the page to be added.
The easiest way is to pass the `IPageInfo` object that describes the page's source document and its number. 

Here are the steps to combine several pages from various documents specifying the pages by their numbers:

*   Create a [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) object and provide the path or stream of the source file.
*   Use the [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) to add another source document. Repeat this step for each document you want to merge.
*   Create a [PageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/) object by calling the `Merger.createPageBuilder` method.
*   Call the [addPage](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/#addPage-com.groupdocs.merger.domain.result.IPageInfo-) method and pass the `IPageInfo` object describing the appropriate page. Note that the `IPageInfo` object uses zero-based notation for both source documents and page numbers.  Repeat this step for every page you want to add.
*   Use the [applyPageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#applyPageBuilder-com.groupdocs.merger.domain.builders.PageBuilder-) method to apply the specified order of pages to the merged document.
*   Save the resulting document by calling the [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and providing a file path.


```java
String filePath = "c:\sample.docx";
String filePath2 = "c:\sample2.docx";
String filePathOut = "c:\output\result.docx";

Merger merger = new Merger(filePath);
{
    merger.join(filePath2);

    PageBuilder pageBuilder = merger.createPageBuilder(null);
    // Add page 1 from the first document
    pageBuilder.addPage(pageBuilder.getDocuments().get(0).getPages()[0]);
    // Add page 3 from the second document
    pageBuilder.addPage(pageBuilder.getDocuments().get(1).getPages()[2]);
    // Add page 4 from the first document 
    pageBuilder.addPage(pageBuilder.getDocuments().get(0).getPages()[3]);
    // Add page 2 from the second document
    pageBuilder.addPage(pageBuilder.getDocuments().get(1).getPages()[1]);
    // Add page 1 from the second document
    pageBuilder.addPage(pageBuilder.getDocuments().get(1).getPages()[0]);
    // Add page 6 from the first document 
    pageBuilder.addPage(pageBuilder.getDocuments().get(1).getPages()[5]);

    // Apply the page order
    merger.applyPageBuilder(pageBuilder);

    merger.save(filePathOut);
}
```

## Specifying the required pages by their index

When adding many pages, specifying them by number is not optimal since in that case each call of the `addPage` method invokes loading of document information. To improve performance, you can skip loading the document information and specify pages by their index instead.

To combine several pages from various documents specifying the pages by their index:

*   Create a [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) object and provide the path or stream of the source file.
*   Use the [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) to add another source document. Repeat this step for each document you want to merge.
*   Create a [PageBuilderOptions](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.options/pagebuilderoptions/) object and set the `LoadDocumentInfo` property to `false`.
*   Create a [PageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/) object by calling the `Merger.createPageBuilder` method and pass the `PageBuilderOptions` to it.
*   Call the [addPage](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/#addPage-int-int-) method and pass the source document index and the index number of the needed page. Repeat this step for every page you want to add.
*   Call the [applyPageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#applyPageBuilder-com.groupdocs.merger.domain.builders.PageBuilder-) method to apply the specified order of pages to the merged document.
*   Save the resulting document by calling the [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and providing a file path.

```java
String filePath = "c:\sample.docx";
String filePath2 = "c:\sample2.docx";
String filePathOut = "c:\output\result.docx";

Merger merger = new Merger(filePath);
{
    merger.join(filePath2);

    PageBuilderOptions pageBuilderOptions = new PageBuilderOptions();
    pageBuilderOptions.setLoadDocumentInfo(false);

    PageBuilder pageBuilder = merger.createPageBuilder(pageBuilderOptions);
    // Add page 1 from the first document
    pageBuilder.addPage(pageBuilder.getDocuments().get(0).getIndex(), 1);
    // Add page 3 from the second document
    pageBuilder.addPage(pageBuilder.getDocuments().get(1).getIndex(), 3);
    // Add page 4 from the first document 
    pageBuilder.addPage(pageBuilder.getDocuments().get(0).getIndex(), 4);
    // Add page 2 from the second document
    pageBuilder.addPage(pageBuilder.getDocuments().get(1).getIndex(), 2);
    // Add page 1 from the second document
    pageBuilder.addPage(pageBuilder.getDocuments().get(1).getIndex(), 1);
    // Add page 6 from the first document 
    pageBuilder.addPage(pageBuilder.getDocuments().get(0).getIndex(), 6);
    
    // Apply the page order
    merger.applyPageBuilder(pageBuilder);

    merger.save(filePathOut);
}
```
## Specifying the range of the required pages

When you need to add multiple pages at once, you can use the `addPageRange` method. It accepts an array of `IPageInfo` objects, each describing the appropriate page.

Here are the steps to combine several pages from various documents specifying them as a range:

*   Create a [Merger](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/) object and provide the path or stream of the source file.
*   Use the [join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-) to add another source document. Repeat this step for each document you want to merge.
*   Create a [PageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/) object by calling the `Merger.createPageBuilder` method.
*   Call the [addPageRange](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.domain.builders/pagebuilder/#addPageRange-com.groupdocs.merger.domain.result.IPageInfo---) method and pass an array of `IPageInfo` objects describing the appropriate pages. Please note that `IPageInfo` objects use zero-based notation for source documents and page numbers.
*   Use the [applyPageBuilder](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#applyPageBuilder-com.groupdocs.merger.domain.builders.PageBuilder-) method to apply the specified order of pages to the merged document.
*   Save the resulting document by calling the [save](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#save-java.io.OutputStream-) method and providing a file path.


```java
String filePath = "c:\sample.docx";
String filePath2 = "c:\sample2.docx";
String filePathOut = "c:\output\result.docx";

Merger merger = new Merger(filePath);
{
    merger.join(filePath2);

    PageBuilder pageBuilder = merger.createPageBuilder(null);
    // Specify a range of pages
        IPageInfo[] range = new IPageInfo[] {
            pageBuilder.getDocuments().get(0).getPages()[0], // Page 1 from the first document
            pageBuilder.getDocuments().get(1).getPages()[2], // Page 3 from the second document
            pageBuilder.getDocuments().get(0).getPages()[3], // Page 4 from the first document
            pageBuilder.getDocuments().get(1).getPages()[1], // Page 2 from the second document
            pageBuilder.getDocuments().get(1).getPages()[0], // Page 1 from the second document
            pageBuilder.getDocuments().get(0).getPages()[5], // Page 6 from the first document
        };
      // Append a page of pages
    pageBuilder.addPageRange(range);

    // Apply the page order
    merger.applyPageBuilder(pageBuilder);

    merger.save(filePathOut);
}
```