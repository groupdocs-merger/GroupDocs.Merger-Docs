---
id: add-document-password
url: merger/python-net/add-document-password
title: Add Document Password
linkTitle: Add Document Password
weight: 1
description: "Encrypt a PDF, Word, Excel, or PowerPoint document by adding an open password using AddPasswordOptions with GroupDocs.Merger for Python via .NET."
keywords: add document password, encrypt document, add PDF password, add Word password, add Excel password, add PowerPoint password, AddPasswordOptions, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you add an open password to any supported document format. Once protected, the document can only be opened by users who supply the correct password.

## Steps to add a document password

1. Instantiate the `Merger` class with the path to the source document.
2. Create an `AddPasswordOptions` instance with the desired password string.
3. Call `merger.add_password()` and pass the `AddPasswordOptions` object.
4. Call `merger.save()` with the output file path to write the protected document.

{{< tabs "add-document-password-example" >}}
{{< tab "add_document_password.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import AddPasswordOptions

def add_document_password():
    # Load the source document
    with Merger("./input.pdf") as merger:
        # Define the password to apply
        options = AddPasswordOptions("p@ss")
        # Encrypt the document with the specified password
        merger.add_password(options)
        # Save the password-protected document
        merger.save("./output.pdf")

if __name__ == "__main__":
    add_document_password()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/security-operations/add-document-password/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 86 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/security-operations/add-document-password/add_document_password/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load Source Document**: The `Merger` class is instantiated with the path to the document that should be protected.
- **Configure Password**: `AddPasswordOptions("p@ss")` sets the password that will be required to open the document.
- **Apply Protection**: `merger.add_password()` encrypts the document using the supplied options.
- **Save Result**: `merger.save()` writes the password-protected file to the specified output path.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on `AddPasswordOptions` and supported formats.

## See also

- [Add password to PDF with permissions]({{< ref "merger/python-net/developer-guide/security-operations/add-password-to-pdf-with-permissions.md" >}})
- [Remove document password]({{< ref "merger/python-net/developer-guide/security-operations/remove-document-password.md" >}})
- [Update document password]({{< ref "merger/python-net/developer-guide/security-operations/update-document-password.md" >}})
