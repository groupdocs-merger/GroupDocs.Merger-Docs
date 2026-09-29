---
id: add-password-to-pdf-with-permissions
url: merger/python-net/add-password-to-pdf-with-permissions
title: Add Password to PDF with Permissions
linkTitle: PDF Password with Permissions
weight: 2
description: "Protect a PDF with an open password and restrict specific operations such as printing using PdfSecurityOptions and PdfSecurityPermissions with GroupDocs.Merger for Python via .NET."
keywords: PDF permissions, add PDF password, restrict printing, deny printing, PdfSecurityOptions, PdfSecurityPermissions, DENY_PRINTING, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you protect a PDF document with an open password and simultaneously restrict specific operations — for example, prevent printing or modification — using `PdfSecurityOptions` combined with `PdfSecurityPermissions`.

## Steps to add a password with permissions to a PDF

1. Instantiate the `Merger` class with the path to the source PDF.
2. Create a `PdfSecurityOptions` instance with the desired password string.
3. Set the `permissions` property to one or more `PdfSecurityPermissions` enum values (e.g. `DENY_PRINTING`).
4. Call `merger.add_password()` and pass the `PdfSecurityOptions` object.
5. Call `merger.save()` with the output file path.

{{< tabs "add-pdf-permissions-example" >}}
{{< tab "add_password_to_pdf_with_permissions.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import PdfSecurityOptions, PdfSecurityPermissions

def add_password_to_pdf_with_permissions():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Create PDF-specific security options with an open password
        security_options = PdfSecurityOptions("p@ss")
        # Deny printing so the recipient cannot print the document
        security_options.permissions = PdfSecurityPermissions.DENY_PRINTING
        # Apply the password and permissions
        merger.add_password(security_options)
        # Save the protected PDF
        merger.save("./output.pdf")

if __name__ == "__main__":
    add_password_to_pdf_with_permissions()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/security-operations/add-password-to-pdf-with-permissions/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 86 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/security-operations/add-password-to-pdf-with-permissions/add_password_to_pdf_with_permissions/output.pdf)
{{< /tab >}}
{{< /tabs >}}

{{< alert style="tip" >}}
`PdfSecurityPermissions` values can be combined using the bitwise OR operator if you need to deny multiple operations at once.
{{< /alert >}}

### Explanation

- **Load Source PDF**: The `Merger` class is instantiated with the PDF to protect.
- **Configure Security Options**: `PdfSecurityOptions("p@ss")` creates an options object that both sets the open password and allows fine-grained permission control.
- **Set Permissions**: Assigning `PdfSecurityPermissions.DENY_PRINTING` to `security_options.permissions` prevents the recipient from printing the document after opening it.
- **Apply and Save**: `merger.add_password()` encrypts the document; `merger.save()` writes the secured PDF to disk.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for the full list of `PdfSecurityPermissions` values.

## See also

- [Add document password]({{< ref "merger/python-net/developer-guide/security-operations/add-document-password.md" >}})
- [Remove document password]({{< ref "merger/python-net/developer-guide/security-operations/remove-document-password.md" >}})
- [Update document password]({{< ref "merger/python-net/developer-guide/security-operations/update-document-password.md" >}})
