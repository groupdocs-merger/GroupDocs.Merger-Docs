---
id: add-password-to-pdf-with-permissions
url: merger/net/add-password-to-pdf-with-permissions
title: Add password to PDF with permissions
weight: 2
description: "This article explains how to add password for PDF document with permissions using GroupDocs.Merger for .NET."
keywords: Add password to PDF with permissions
productName: GroupDocs.Merger for .NET
hideChildren: False
---
You can easy protect PDF document with permissions, using the "GroupDocs.Merger for .NET" product.

The following example demonstrates how to secure PDF document with permissions in C# code:

*   Initialize [PdfSecurityOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/PdfSecurityOptions) class with new document password and set Permissions property with enum value of [PdfSecurityPermissions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/PdfSecurityPermissions);
*   Instantiate [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) object with source document path or stream;
*   Call [AddPassword](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/addpassword) method and pass [PdfSecurityOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/PdfSecurityOptions) object to it;
*   Call [Save](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/save/#save_1) method specifying file path to save resultant document.

```csharp
string filePath = @"c:\sample.pdf";
string filePathOut = @"c:\output\result.pdf";

PdfSecurityOptions pdfSecurityOptions = new PdfSecurityOptions("SAMPLE_PASSWORD");
pdfSecurityOptions.Permissions = PdfSecurityPermissions.DenyModification;

using (Merger merger = new Merger(filePath))
{
    merger.AddPassword(pdfSecurityOptions);
    merger.Save(filePathOut);
}
```