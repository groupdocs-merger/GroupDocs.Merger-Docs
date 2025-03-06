---
id: add-document-password
url: merger/python-net/add-document-password
title: Add document password
weight: 1
description: "This article explains how to add document password for PDF, Word, Excel, PowerPoint and  other file types using GroupDocs.Merger for .NET."
keywords: Add document password, Add PDF password, Add Word password, Add Excel password, Add PowerPoint password
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**GroupDocs.Merger** allows to add document password. Here are the steps to add document password:

*   Initialize [AddPasswordOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/addpasswordoptions) class with new document password;
*   Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger) object with source document path or stream;
*   Call [AddPassword](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/addpassword) method and pass [AddPasswordOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/addpasswordoptions) object to it;
*   Call [Save](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/save/#save_1) method specifying file path to save resultant document.

The following code sample demonstrates how to add document password.

```python
with gm.Merger(constants.sample_pptx) as merger:
    add_password_options = gm.domain.options.AddPasswordOptions("SomePasswordString")
    merger.add_password(add_password_options)
    merger.save(constants.output_pptx)
```
