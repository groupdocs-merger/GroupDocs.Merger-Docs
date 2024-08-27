---
id: merge-documents-to-pdf
url: merger/net/merge-documents-to-pdf
title: Merge documents to PDF
weight: 140
description: "This section describes how to import OLE objects into PDF documents using C#/.NET"
keywords: 
productName: GroupDocs.Merger for .NET
hideChildren: False
---
## Introduction

Consider the functionality for merging files of various formats such as [PDF](https://docs.fileformat.com/view/pdf/) / [XPS](https://docs.fileformat.com/page-description-language/xps/), [DOC](https://docs.fileformat.com/word-processing/doc/), [PPT](https://docs.fileformat.com/presentation/ppt/) and [XLS](https://docs.fileformat.com/spreadsheet/xls/) into a PDF document. Let's see, why do we need to combine these files into a PDF document? This article discusses the PDF format, but those ones will be more in the near future. But turn back to the PDF format. It is a standard format that allows you to display information the same on any device with any platform. It is comfortable for transferring info via the Internet or to a printer. That is why this format is chosen for the current task of combining files of various formats.

## Merge documents to PDF / XPS

Multiple files (even different types of files such as [DOC](https://docs.fileformat.com/word-processing/doc/), [PPT](https://docs.fileformat.com/presentation/ppt/), [XLS](https://docs.fileformat.com/spreadsheet/xls/)) can be combined into a single PDF / XPS file by using **[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** API. You can also use this [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) method to combine multiple PDF / XPS files. This cross-format merge to PDF / XPS could be useful for the cases when there is no ability to merge only PDF / XPS files. For now, GroupDocs.Merger API allows to [Join](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/join) other file types without password with the PDF / XPS document loaded into [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object.

The following example demonstrates how to merge PDF file with [DOC](https://docs.fileformat.com/word-processing/doc/), [PPT](https://docs.fileformat.com/presentation/ppt/) and [XLS](https://docs.fileformat.com/spreadsheet/xls/) file types:

```csharp
using (Merger merger = new Merger(@"c:\document1.pdf"))
{
    merger.Join(@"c:\document2.doc");
    merger.Join(@"c:\document3.ppt");
    merger.Join(@"c:\document4.xls");
    merger.Save(@"c:\merged.pdf");
}
```

Also, please read the following article: [How to correctly merge streams to PDF]({{< ref "merger/net/getting-started/use-cases/how-to-correctly-merge-documents-using-csharp.md" >}})