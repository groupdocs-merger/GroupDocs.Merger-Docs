---
id: merge-documents-to-doc
url: merger/net/merge-documents-to-doc
title: Merge documents to DOC
weight: 101
description: "This section describes how to import OLE objects into Word DOC/DOCX documents using C#/.NET"
keywords: 
productName: GroupDocs.Merger for .NET
hideChildren: False
---
## Introduction

Consider the functionality for merging files of various formats such as [DOC](https://docs.fileformat.com/word-processing/doc/), [PDF](https://docs.fileformat.com/view/pdf/), [XPS](https://docs.fileformat.com/page-description-language/xps/), [EPUB](https://docs.fileformat.com/ebook/epub/) and [TEX](https://docs.fileformat.com/page-description-language/tex/) into a DOC document. Let's see, why do we need to combine these files into a DOC document? This article discusses the DOC format, but those ones will be more in the near future. But turn back to the DOC format. It is a standard format that allows you to display information the same on any device with any platform. It is comfortable for transferring info via the Internet or to a printer. That is why this format is chosen for the current task of combining files of various formats.

## Merge documents to DOC / DOCX

Multiple files (even different types of PDF files such as [PDF](https://docs.fileformat.com/view/pdf/), [XPS](https://docs.fileformat.com/page-description-language/xps/), [EPUB](https://docs.fileformat.com/ebook/epub/) and [TEX](https://docs.fileformat.com/page-description-language/tex/)) can be combined into a single DOC / DOCX file by using **[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** API. You can also use this [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method to combine multiple DOC / DOCX files. This cross-format merge to DOC / DOCX could be useful for the cases when there is no ability to merge only DOC files. For now, GroupDocs.Merger API allows to [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) other file types without password with the DOC / DOCX document loaded into [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object.

The following example demonstrates how to merge DOC file with [PDF](https://docs.fileformat.com/view/pdf/), [XPS](https://docs.fileformat.com/page-description-language/xps/), [EPUB](https://docs.fileformat.com/ebook/epub/) and [TEX](https://docs.fileformat.com/page-description-language/tex/) file types:

```csharp
using (Merger merger = new Merger(@"c:\document1.doc"))
{
    merger.Join(@"c:\document2.pdf");
    merger.Join(@"c:\document3.xps");
    merger.Join(@"c:\document4.epub");
    merger.Join(@"c:\document5.tex");
 
	merger.Save(@"c:\merged.doc");
}
```

