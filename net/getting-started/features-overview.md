---
id: features-overview
url: merger/net/features-overview
title: Features Overview
weight: 1
description: "This artice decsribes the features of GroupDocs.Merger for .NET library. It allows you to Merge PDF, Merge JPG, Split Document, Move Page, Swap Pages of the documents."
keywords: Merge PDF, Merge JPG, Split Document, Move Page, Swap Pages
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: true
---
GroupDocs.Merger allows you to join multiple documents and manipulate single document structure across wide range of [supported document types]({{< ref "merger/net/getting-started/supported-document-formats.md" >}}), [supported audio types]({{< ref "merger/net/getting-started/supported-audio-formats.md" >}}), [supported archive types]({{< ref "merger/net/getting-started/supported-archive-formats.md" >}}) and [supported cross-merging types]({{< ref "merger/net/getting-started/supported-cross-merging-formats.md" >}}). Below, the short list of possible actions:

## Multiple document operations 

### Join Documents

This feature lets you [merge]({{< ref "merger/net/developer-guide/merge/_index.md" >}}) two or more documents into one document, join specific pages or page ranges from several source documents into single resultant document.

## Single document operations

### Split Document

**Split** operation allows to [divide]({{< ref "merger/net/developer-guide/single-document-operations/split-document.md" >}}) a source document to several resultant documents.

### Move Page

**MovePage** allows to [move page]({{< ref "merger/net/developer-guide/single-document-operations/move-page.md" >}}) to another position within a document.

### Remove Pages

**RemovePages** feature provides an ability to [remove]({{< ref "merger/net/developer-guide/single-document-operations/remove-pages.md" >}}) single page or a collection of specific page numbers from the source document.

### Rotate Pages

**RotatePages** operation lets you [rotate pages]({{< ref "merger/net/developer-guide/single-document-operations/rotate-pages.md" >}}) within document. You can rotate pages by setting rotation angle to 90,180 or 270 degrees.

### Swap Pages

**SwapPages** operation allows to [swap]({{< ref "merger/net/developer-guide/single-document-operations/swap-pages.md" >}}) two pages positions within the source document. The result is a new document where two pages have their positions exchanged.

### Extract Pages

**ExtractPages** feature allows to [extract]({{< ref "merger/net/developer-guide/single-document-operations/extract-pages.md" >}}) specified page or page ranges from source document. The result is a new document that contains only specified pages from the source document.

### Change Pages Orientation

**ChangeOrientation** operation lets you [set page orientation]({{< ref "merger/net/developer-guide/single-document-operations/change-page-orientation.md" >}}) (portrait, landscape) for specific or all pages of the document.

## Document security operations

GroupDocs.Merger API allows to manage document password-protection through the following security operations:

* [Check for password-protection]({{< ref "merger/net/developer-guide/security-operations/check-document-password-protection.md" >}});
* [Set document password]({{< ref "merger/net/developer-guide/security-operations/add-document-password.md" >}}) if document is not protected with password;
* [Update password]({{< ref "merger/net/developer-guide/security-operations/update-document-password.md" >}}) if document is password-protected already;
* [Remove password]({{< ref "merger/net/developer-guide/security-operations/remove-document-password.md" >}}) if document is password-protected.

## Document information extraction

GroupDocs.Merger allows to obtain basic information about source document - file type, size, pages count, page height and width etc.  
This may be quite useful for generating document preview.

## Preview document pages

Document preview feature allows to generate image representations of document pages. This may be helpful for better understanding about document content and its structure. Preview can be generated for all document pages (by default) or for specific page numbers or page range.

Supported image formats for document preview are:

* PNG;
* JPG;
* BMP.

## Logging while processing document

GroupDocs.Merger allows to log document manipulation processes info through [ILogger](https://reference.groupdocs.com/merger/net/groupdocs.merger.logging/ilogger) interface. There is ability to use built-in [ConsoleLogger](https://reference.groupdocs.com/merger/net/groupdocs.merger.logging/consolelogger) or implement own logging logic.
