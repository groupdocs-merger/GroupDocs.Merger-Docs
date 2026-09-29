---
id: remove-document-password
url: merger/python-net/remove-document-password
title: Remove Document Password
linkTitle: Remove Document Password
weight: 4
description: "Decrypt and remove the open password from a PDF, Word, Excel, or PowerPoint document using remove_password() with GroupDocs.Merger for Python via .NET."
keywords: remove document password, decrypt document, remove PDF password, remove Word password, remove Excel password, remove PowerPoint password, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you remove an open password from a protected document. After the operation the saved document is unencrypted and can be opened without any password.

## Steps to remove a document password

1. Create a `LoadOptions` instance and supply the current password so the document can be opened.
2. Instantiate the `Merger` class with the protected document path and the `LoadOptions` object.
3. Call `merger.remove_password()` to strip the password.
4. Call `merger.save()` with the output file path to write the decrypted document.

{{< tabs "remove-document-password-example" >}}
{{< tab "remove_document_password.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import LoadOptions

def remove_document_password():
    # Supply the current password so the protected document can be opened
    load_options = LoadOptions(password="p@ss")
    # Load the password-protected document
    with Merger("./protected.pdf", load_options) as merger:
        # Remove the open password from the document
        merger.remove_password()
        # Save the decrypted (unprotected) document
        merger.save("./output.pdf")

if __name__ == "__main__":
    remove_document_password()
```
{{< /tab >}}
{{< tab "protected.pdf" >}}
{{< tab-text >}}
`protected.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/security-operations/remove-document-password/protected.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 85 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/security-operations/remove-document-password/remove_document_password/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load Options**: `LoadOptions(password="p@ss")` provides the current document password so that `Merger` can decrypt and open the file. Omitting the password when the document is protected raises `IncorrectPasswordException`.
- **Load Document**: The `Merger` context manager opens the protected file using the supplied credentials.
- **Remove Password**: `merger.remove_password()` clears the open password from the in-memory document representation.
- **Save Result**: `merger.save()` writes the now-unprotected document to disk.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on `remove_password()` and `LoadOptions`.

## See also

- [Add document password]({{< ref "merger/python-net/developer-guide/security-operations/add-document-password.md" >}})
- [Update document password]({{< ref "merger/python-net/developer-guide/security-operations/update-document-password.md" >}})
- [Check document password protection]({{< ref "merger/python-net/developer-guide/security-operations/check-document-password-protection.md" >}})
