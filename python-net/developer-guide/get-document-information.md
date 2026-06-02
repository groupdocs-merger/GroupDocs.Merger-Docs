---
id: get-document-information
url: merger/python-net/get-document-information
title: Get Document Information
linkTitle: Get Document Information
weight: 2
description: "Retrieve the file type, page count, file size, and per-page dimensions of any supported document using get_document_info() with GroupDocs.Merger for Python via .NET."
keywords: get document information, document info, page count, file type, page width, page height, IDocumentInfo, IPageInfo, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you retrieve metadata about any supported document without performing any merge or split operation. The `get_document_info()` method returns an `IDocumentInfo` object that exposes:

- **`info.type`** — a `FileType` object describing the format (`.file_format` for the human-readable name, `.extension` for the file extension).
- **`info.page_count`** — total number of pages.
- **`info.size`** — file size in bytes.
- **`info.pages`** — a list of `IPageInfo` objects; each exposes `.number`, `.width`, `.height`, and `.visible`.

## Steps to get document information

1. Instantiate the `Merger` class with the path to the document.
2. Call `merger.get_document_info()` to obtain the `IDocumentInfo` object.
3. Read the desired properties from the returned object.

{{< tabs "get-document-information-example" >}}
{{< tab "read_document_info.py" >}}
```python
from groupdocs.merger import Merger

def read_document_info():
    # Load the document whose information should be retrieved
    with Merger("./input.pdf") as merger:
        # Obtain the document information object
        info = merger.get_document_info()
        # Print file type details
        print("Type:", info.type.file_format)
        # Print overall document statistics
        print("Pages:", info.page_count, "Size:", info.size, "bytes")
        # Iterate over individual page metadata
        for page in info.pages:
            print(f"  page {page.number}: {page.width}x{page.height}")

if __name__ == "__main__":
    read_document_info()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/get-document-information/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "read-document-info.txt" >}}  
```text
Type: Portable Document Format File
Pages: 2 Size: 86913 bytes
  page 1: 595x841
  page 2: 595x841
```
[Download full output](/merger/python-net/_output_files/developer-guide/get-document-information/read_document_info/read-document-info.txt)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load Document**: The `Merger` context manager opens the document at the given path.
- **Retrieve Info**: `merger.get_document_info()` reads the document metadata and returns an `IDocumentInfo` instance.
- **File Type**: `info.type.file_format` returns a descriptive string such as `"Portable Document Format File"`. Use `info.type.extension` to get the dot-prefixed extension (e.g. `".pdf"`).
- **Page Count and Size**: `info.page_count` gives the total page count; `info.size` gives the file size in bytes.
- **Page Details**: Iterating `info.pages` provides per-page `IPageInfo` objects. Each exposes `.number` (1-based), `.width`, and `.height` (in document units), and `.visible` (whether the page is visible).

{{< alert style="info" >}}
Use `info.type`, not `info.type_`. The underscore form is a stale alias that no longer exists in the current API.
{{< /alert >}}

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on `IDocumentInfo` and `IPageInfo`.

## See also

- [Get supported file types]({{< ref "merger/python-net/developer-guide/get-supported-file-types.md" >}})
- [Generate page previews]({{< ref "merger/python-net/developer-guide/page-preview.md" >}})
- [Load password-protected documents]({{< ref "merger/python-net/developer-guide/loading-documents/load-password-protected.md" >}})
