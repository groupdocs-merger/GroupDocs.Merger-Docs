---
id: check-document-password-protection
url: merger/python-net/check-document-password-protection
title: Check Document Password Protection
linkTitle: Check Password Protection
weight: 3
description: "Determine whether a PDF, Word, Excel, or PowerPoint document has an open password set using the is_password_set() method of GroupDocs.Merger for Python via .NET."
keywords: check document password, is password set, password protection, check PDF protected, check Word password, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you check whether a document has an open password set. The `is_password_set()` method on the `Merger` instance returns `True` if the document requires a password to open, or `False` otherwise.

## Steps to check document password protection

1. Open the document with `Merger`. If the document is already password-protected, supply the password via `LoadOptions`; otherwise omit it.
2. Call `merger.is_password_set()` and inspect the return value.

{{< tabs "check-password-example" >}}
{{< tab "check_document_password_protection.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import LoadOptions

def check_document_password_protection():
    # Provide the current password so the protected document can be opened
    load_options = LoadOptions(password="p@ss")
    # Load the password-protected document
    with Merger("./protected.pdf", load_options) as merger:
        # Returns True if the document has an open password set
        protected = merger.is_password_set()
        print("Is password set:", protected)

if __name__ == "__main__":
    check_document_password_protection()
```
{{< /tab >}}
{{< tab "protected.pdf" >}}
{{< tab-text >}}
`protected.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/security-operations/check-document-password-protection/protected.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "check-document-password-protection.txt" >}}  
```text
Is password set: True
```
[Download full output](/merger/python-net/_output_files/developer-guide/security-operations/check-document-password-protection/check_document_password_protection/check-document-password-protection.txt)
{{< /tab >}}
{{< /tabs >}}

{{< alert style="info" >}}
`is_password_set()` is a method on the `Merger` instance, not a property of the document information object returned by `get_document_info()`.
{{< /alert >}}

### Explanation

- **Supply Load Password**: `LoadOptions(password="p@ss")` allows `Merger` to open the encrypted document. Without this, opening a protected document raises `IncorrectPasswordException`.
- **Load Document**: The `Merger` context manager opens the document using the provided credentials.
- **Check Protection**: `merger.is_password_set()` interrogates the loaded document and returns `True` if an open password is present, `False` if the document is unprotected.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for more details on `is_password_set()` and `LoadOptions`.

## See also

- [Add document password]({{< ref "merger/python-net/developer-guide/security-operations/add-document-password.md" >}})
- [Remove document password]({{< ref "merger/python-net/developer-guide/security-operations/remove-document-password.md" >}})
- [Load password-protected documents]({{< ref "merger/python-net/developer-guide/loading-documents/load-password-protected.md" >}})
