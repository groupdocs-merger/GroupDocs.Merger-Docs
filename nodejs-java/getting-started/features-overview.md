---
id: features-overview
url: merger/nodejs-java/features-overview
title: Features overview
weight: 1
description: "GroupDocs.Merger for Node.js via Java is a powerful API to merge several documents into one, split single document to multiple documents, reorder or replace document pages, change page orientation, manage document protection, render documents as images and more."
keywords: merge files,join documents,merger
productName: GroupDocs.Merger for Node.js via Java
hideChildren: False
toc: True
---
  
## Node.js Merger API Features 
- Join two or more documents into one document, join specific pages or page ranges from several source documents into single resultant document.
- Split a source document to several resultant documents.
- Move page to another position within a document.
- Remove single page or a collection of specific page numbers from the source document.
- Rotate pages within document by setting rotation angle to 90,180 or 270 degrees.
- Swap two pages positions within the source document. The result is a new document where two pages have their positions exchanged.
- Extract specified page or page ranges from source document. The result is a new document that contains only specified pages from the source document.
- Change orientation operation lets to set page orientation (portrait, landscape) for specific or all pages of the document.
- Manage document password protection: add/update/delete document password and check its existence.
- Get the basic information about source document - file type, size, pages count, page height and width etc.
- Document preview feature allows to generate image representations of document pages. This may be helpful for better understanding about document content and its structure. Preview can be generated for all document pages (by default) or for specific page numbers or page range.

## Caching results

GroupDocs.Merger for Node.js provides a document merger API that supports caching in order to boost document loading speed and optimize application performance.

Documents cache is saved to a local disk by default. However, document merger API also provides document cache interfaces that can be implemented for 3rd party storage support - FTP, Amazon S3, Dropbox, Google Drive, Microsoft Azure, Redis or any other.
