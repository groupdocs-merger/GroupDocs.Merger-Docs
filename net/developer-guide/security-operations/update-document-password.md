---
id: update-document-password
url: merger/net/update-document-password
title: Update document password
weight: 4
description: "This article explains how to update password for PDF, Word, Excel, PowerPoint documents by using GroupDocs.Merger for .NET."
keywords: Update document password protection, Update PDF password, Update Word document password, Update Excel spreadsheet password, Update PowerPoint password
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** allows to update password from password-protected document. The resultant document will have new password.  
Here are the steps to update document password:

*   Initialize [LoadOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/loadoptions) class specifying current password;
*   Instantiate [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) object with source document path or stream and pass [LoadOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/loadoptions) object to it;
*   Initialize [UpdatePasswordOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/updatepasswordoptions) class specifying new document password;
*   Call [UpdatePassword](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger/methods/updatepassword) method and pass [UpdatePasswordOptions](https://apireference.groupdocs.com/net/merger/groupdocs.merger.domain.options/updatepasswordoptions) object to it;
*   Call [Save](https://apireference.groupdocs.com/net/merger/groupdocs.merger.merger/save/methods/1) method specifying file path to save resultant document.

The following code sample demonstrates how to update document password:

```csharp
string filePath = @"c:\sample.xlsx";
string filePathOut = @"c:\output\result.xlsx";

ILoadOptions loadOptions = new LoadOptions("SAMPLE_PASSWORD");
IUpdatePasswordOptions updateOptions = new UpdatePasswordOptions("NEW_SAMPLE_PASSWORD");

using (Merger merger = new Merger(filePath, loadOptions))
{
    merger.UpdatePassword(updateOptions);
    merger.Save(filePathOut);
}
```
