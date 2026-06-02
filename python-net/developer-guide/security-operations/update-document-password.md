---
id: update-document-password
url: merger/python-net/update-document-password
title: Update Document Password
linkTitle: Update Document Password
weight: 5
description: "Replace the existing open password of a PDF, Word, Excel, or PowerPoint document with a new password using UpdatePasswordOptions with GroupDocs.Merger for Python via .NET."
keywords: update document password, change document password, update PDF password, update Word password, update Excel password, UpdatePasswordOptions, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you replace an existing open password on a protected document with a new one. The saved document will require the new password to open.

## Steps to update a document password

1. Create a `LoadOptions` instance and supply the *current* password so the document can be opened.
2. Instantiate the `Merger` class with the protected document path and the `LoadOptions` object.
3. Create an `UpdatePasswordOptions` instance with the *new* password string.
4. Call `merger.update_password()` and pass the `UpdatePasswordOptions` object.
5. Call `merger.save()` with the output file path to write the re-encrypted document.

{{< tabs "update-document-password-example" >}}
{{< tab "update_document_password.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import LoadOptions, UpdatePasswordOptions

def update_document_password():
    # Supply the current (old) password so the protected document can be opened
    load_options = LoadOptions(password="old_p@ss")
    # Load the password-protected document
    with Merger("./protected.pdf", load_options) as merger:
        # Define the replacement password
        update_options = UpdatePasswordOptions("new_p@ss")
        # Apply the new password to the document
        merger.update_password(update_options)
        # Save the document encrypted with the new password
        merger.save("./output.pdf")

if __name__ == "__main__":
    update_document_password()
```
{{< /tab >}}
{{< tab "protected.pdf" >}}
{{< tab-text >}}
`protected.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/security-operations/update-document-password/protected.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 87 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/security-operations/update-document-password/update_document_password/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load Options**: `LoadOptions(password="old_p@ss")` provides the current document password so that `Merger` can decrypt and open the file. If the wrong password is provided, `IncorrectPasswordException` is raised.
- **Load Document**: The `Merger` context manager opens the protected file using the current credentials.
- **Configure New Password**: `UpdatePasswordOptions("new_p@ss")` wraps the replacement password.
- **Apply Update**: `merger.update_password()` replaces the old password with the new one in the in-memory document.
- **Save Result**: `merger.save()` writes the document encrypted with the new password to disk.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on `UpdatePasswordOptions` and `LoadOptions`.

## See also

- [Add document password]({{< ref "merger/python-net/developer-guide/security-operations/add-document-password.md" >}})
- [Remove document password]({{< ref "merger/python-net/developer-guide/security-operations/remove-document-password.md" >}})
- [Check document password protection]({{< ref "merger/python-net/developer-guide/security-operations/check-document-password-protection.md" >}})
