---
id: load-password-protected
url: merger/python-net/developer-guide/loading-documents/load-password-protected
title: Load Password-Protected Document
linkTitle: Load Password-Protected
weight: 3
description: "Open encrypted PDF, Word, Excel, and PowerPoint documents by passing a LoadOptions instance with the password parameter to the Merger constructor in GroupDocs.Merger for Python via .NET."
keywords: password-protected document, load password, LoadOptions, IncorrectPasswordException, PasswordRequiredException, encrypted document, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) supports opening documents that are protected with an open password. To unlock the file, pass a `LoadOptions` instance — populated with the correct password — to the `Merger` constructor alongside the file path or stream.

## Exception handling

If the document is protected and you do not supply a password, or if the supplied password is incorrect, the library raises one of the following exceptions from `groupdocs.merger.exceptions`:

- **`PasswordRequiredException`** — raised when you try to open a protected document without providing any password.
- **`IncorrectPasswordException`** — raised when the provided password does not match the document's open password.

## Steps to load a password-protected document

1. Create a `LoadOptions` instance and set the `password` parameter to the document's open password.
2. Instantiate the `Merger` class with both the document path and the `LoadOptions` object.
3. Perform any supported operation (merge, split, get info, etc.) on the open document.

{{< tabs "load-password-protected-example" >}}
{{< tab "load_password_protected.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import LoadOptions
from groupdocs.merger.exceptions import IncorrectPasswordException, PasswordRequiredException

def load_password_protected():
    # Provide the document's open password via LoadOptions
    load_options = LoadOptions(password="secret")
    try:
        # Load the password-protected document
        with Merger("./protected.pdf", load_options) as merger:
            # The document is now open — perform any supported operation
            info = merger.get_document_info()
            print("Format:", info.type.file_format)
            print("Pages:", info.page_count)
    except PasswordRequiredException:
        print("Error: the document requires a password but none was provided.")
    except IncorrectPasswordException:
        print("Error: the supplied password is incorrect.")

if __name__ == "__main__":
    load_password_protected()
```
{{< /tab >}}
{{< tab "protected.pdf" >}}
{{< tab-text >}}
`protected.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/loading-documents/load-password-protected/protected.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "load-password-protected.txt" >}}  
```text
Format: Portable Document Format File
Pages: 2
```
[Download full output](/merger/python-net/_output_files/developer-guide/loading-documents/load-password-protected/load_password_protected/load-password-protected.txt)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load Options**: `LoadOptions(password="secret")` wraps the open password. This options object is passed to the `Merger` constructor so the library can decrypt the document on load.
- **Open Document**: `Merger("./protected.pdf", load_options)` opens the encrypted file. If the password is missing or wrong, the appropriate exception is raised before the `with` block body executes.
- **Perform Operations**: Once open, you can call any `Merger` method — `get_document_info()`, `join()`, `split()`, `save()`, etc. — on the decrypted document.
- **Exception Handling**: Wrapping the `Merger` construction in `try/except` blocks lets you give users a clear error message when the password is absent (`PasswordRequiredException`) or wrong (`IncorrectPasswordException`). Both are importable from `groupdocs.merger.exceptions`.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on `LoadOptions` and the exception hierarchy.

## See also

- [Load from local disk]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-local-disk.md" >}})
- [Load from stream]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-stream.md" >}})
- [Check document password protection]({{< ref "merger/python-net/developer-guide/security-operations/check-document-password-protection.md" >}})
- [Remove document password]({{< ref "merger/python-net/developer-guide/security-operations/remove-document-password.md" >}})
