---
id: get-supported-file-types
url: merger/python-net/get-supported-file-types
title: Get Supported File Types
linkTitle: Get Supported File Types
weight: 1
description: "Enumerate all 72 document formats supported by GroupDocs.Merger for Python via .NET using FileType.get_supported_file_types()."
keywords: supported file types, file formats, FileType, get_supported_file_types, file extension, file format name, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) supports over 70 document formats. You can retrieve the complete list at runtime by calling `FileType.get_supported_file_types()`, which returns a collection of `FileType` objects. Each object exposes:

- **`ft.file_format`** — human-readable format name (e.g. `"Portable Document Format File"`).
- **`ft.extension`** — dot-prefixed file extension (e.g. `".pdf"`).

## Steps to list supported file types

1. Import `FileType` from `groupdocs.merger.domain`.
2. Call `FileType.get_supported_file_types()` to obtain the collection.
3. Iterate and read `file_format` and `extension` from each `FileType` object.

{{< tabs "get-supported-file-types-example" >}}
{{< tab "list_supported_file_types.py" >}}
```python
from groupdocs.merger.domain import FileType

def list_supported_file_types():
    # Retrieve the complete collection of supported file types
    supported_types = FileType.get_supported_file_types()
    # Print the format name and extension for each supported type
    for ft in supported_types:
        print(ft.file_format, ft.extension)

if __name__ == "__main__":
    list_supported_file_types()
```
{{< /tab >}}
{{< tab "list-supported-file-types.txt" >}}  
```text
Zipped File .zip
G-Zip Compressed File .gz
7-Zip Compressed File .7z
Consolidated Unix File Archive .tar
Roshal ARchive Compressed File .rar
Bzip2 Compressed File .bz2
Visio Drawing File .vsd
Visio Drawing .vsdx
Visio Stencil File .vss
Visio Stencil File .vssx
[TRUNCATED]
```
[Download full output](/merger/python-net/_output_files/developer-guide/get-supported-file-types/list_supported_file_types/list-supported-file-types.txt)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Import FileType**: `FileType` is imported from `groupdocs.merger.domain` (not from `groupdocs.merger.domain.options`).
- **Retrieve Collection**: `FileType.get_supported_file_types()` is a static method that returns all formats the library can handle for merge, split, and other operations.
- **Print Details**: Each `FileType` element exposes `.file_format` for a descriptive name and `.extension` for the dot-prefixed extension. Additional boolean properties such as `.is_image`, `.is_archive`, and `.is_text` allow programmatic format categorisation.

{{< alert style="tip" >}}
You can filter the results by format family using the boolean properties on `FileType`, for example `[ft for ft in supported_types if ft.is_image]` to get only image formats.
{{< /alert >}}

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for the full `FileType` property list and the complete table of [Supported Document Formats]({{< ref "merger/python-net/getting-started/supported-document-formats.md" >}}).

## See also

- [Get document information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}})
- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
