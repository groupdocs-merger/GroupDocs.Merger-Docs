---
id: save-document
url: merger/net/save-document
title: Save document
weight: 3
description: "This guide describes how to save document of PDF, Word, Excel, PowerPoint and many other formats into one resultant document using GroupDocs.Merger API."
keywords: Save document, Save PDF, Save DOCX, Save PPTX, Save XSLX
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**GroupDocs.Merger** allows to save PDF resultant document by specifying accesibility settings [PdfAccesibilitySettings](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pdfaccesibilitysettings).

There is an ability to set parameter [EnableAutoTagging](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pdfaccesibilitysettings/enableautotagging) in order to enable auto tagging mode.

The steps to save document with auto tagging mode are the following:

*   Initialize [PdfSaveOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pdfsaveoptions) class and set parameter [EnableAutoTagging](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pdfaccesibilitysettings/enableautotagging) as True;
*   Instantiate [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object with source document path or stream;
*   Call [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save) method and pass [PdfSaveOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/pdfsaveoptions) object to save a resultant document.

## Save the PDF document with auto tagging mode

The following code sample demonstrates how to save PDF document with auto tagging mode:

```csharp
string filePath = @"c:\sample.pdf";
string filePathOut = @"c:\result.pdf";

PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.AccesibilitySettings.EnableAutoTagging = true;
           
using (Merger merger = new Merger(filePath))
{
     merger.Save(filePathOut, pdfSaveOptions);
}  
```

## Save any document by default

The following code sample demonstrates how to save any document by default:

```csharp
string filePath = @"c:\sample.docx";
string filePathOut = @"c:\result.docx";

using (Merger merger = new Merger(filePath))
{
     merger.Save(filePathOut);
}  
```