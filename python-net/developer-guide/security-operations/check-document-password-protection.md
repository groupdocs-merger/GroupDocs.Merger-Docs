---
id: check-document-password-protection
url: merger/python-net/check-document-password-protection
title: Check document password-protection
weight: 3
description: "This article explains how to check whether PDF, Word, Excel, PowerPoint document is password protected or not, and how to do this using GroupDocs.Merger for .NET."
keywords: Check document password protection, Check PDF protected, Check Word document protected, Check Excel document protected
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/python-net)** allows to check document for password-protection. The result will be **true** if document has password for opening set, in other case **false** will be returned.

Here are the steps to check document password-protection:

*   Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger) object with source document path or stream;
*   Call [IsPasswordSet](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/ispasswordset) method.

The following code sample demonstrates how to check document password-protection.

```python
with gm.Merger(constants.sample_xlsx_protected) as merger:
        is_password_set = merger.is_password_set()
```
