---
id: update-document-password
url: merger/python-net/update-document-password
title: Update document password
weight: 5
description: "This article explains how to update password for PDF, Word, Excel, PowerPoint documents by using GroupDocs.Merger for .NET."
keywords: Update document password protection, Update PDF password, Update Word document password, Update Excel spreadsheet password, Update PowerPoint password
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/python-net)** allows to update password from password-protected document. The resultant document will have new password.  
Here are the steps to update document password:

*   Initialize [LoadOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/loadoptions) class specifying current password;
*   Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger) object with source document path or stream and pass [LoadOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/loadoptions) object to it;
*   Initialize [UpdatePasswordOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/updatepasswordoptions) class specifying new document password;
*   Call [UpdatePassword](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/updatepassword) method and pass [UpdatePasswordOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/updatepasswordoptions) object to it;
*   Call [Save](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/save/#save_1) method specifying file path to save resultant document.

The following code sample demonstrates how to update document password:

```python
load_options = gm.domain.options.LoadOptions("SomePasswordString")
with gm.Merger(constants.sample_xlsx_protected, load_options) as merger:
    update_password_options = gm.domain.options.UpdatePasswordOptions("OtherPasswordString")
    merger.update_password(update_password_options)
    merger.save(constants.output_xlsx)
```
