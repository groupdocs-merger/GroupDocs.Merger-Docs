---
id: load-from-local-disk
url: merger/python-net/developer-guide/loading-documents/load-from-local-disk
title: Load Document from Local Disk
linkTitle: Load From Local Disk
weight: 1
description: "Instantiate the Merger class with an absolute or relative file path to load a document stored on the local filesystem with GroupDocs.Merger for Python via .NET."
keywords: load from local disk, file path, Merger constructor, load file, local filesystem, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

To load a source document from the local filesystem, pass a file path to the `Merger` class constructor. GroupDocs.Merger for Python via .NET provides several constructor overloads to cover different loading scenarios:

- `Merger(file_path)` — open a document by path with default settings.
- `Merger(file_path, load_options)` — open a document by path and supply additional loading options (e.g. a password for protected files).
- `Merger(file_path, load_options, settings)` — open a document by path with load options and custom `MergerSettings`.

You can use either an absolute or a relative path. If the specified path does not exist, an exception is raised when the first operation is performed.

{{< alert style="tip" >}}
GroupDocs.Merger accesses the file only when an action (e.g. `get_document_info()`, `join()`, `save()`) is performed on the `Merger` instance.
{{< /alert >}}

The following example demonstrates loading a PDF document from a local path and inspecting its metadata:

{{< tabs "load-from-local-disk-example" >}}
{{< tab "load_from_local_disk.py" >}}
```python
from groupdocs.merger import Merger

def load_from_local_disk():
    # Provide a relative or absolute path to the source document
    with Merger("./input.pdf") as merger:
        # Retrieve document information to confirm the file loaded correctly
        info = merger.get_document_info()
        print("Format:", info.type.file_format)
        print("Pages:", info.page_count)
        print("Size:", info.size, "bytes")

if __name__ == "__main__":
    load_from_local_disk()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/loading-documents/load-from-local-disk/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "load-from-local-disk.txt" >}}  
```text
Format: Portable Document Format File
Pages: 2
Size: 86913 bytes
```
[Download full output](/merger/python-net/_output_files/developer-guide/loading-documents/load-from-local-disk/load_from_local_disk/load-from-local-disk.txt)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **File Path**: The `Merger` constructor accepts the path `"./input.pdf"` and stores it internally. The file is not opened until an action is performed.
- **Context Manager**: The `with` statement ensures that all unmanaged resources (file handles, .NET objects) are released automatically when the block exits, even if an exception occurs.
- **Inspect Metadata**: `merger.get_document_info()` opens the file, reads its metadata, and returns an `IDocumentInfo` object. The example prints the human-readable format name (`info.type.file_format`), total page count, and file size in bytes.

{{< alert style="warning" >}}
GroupDocs.Merger determines the file type by its extension. Make sure the source file has the correct extension; otherwise the library may misdetect the format.
{{< /alert >}}

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on the `Merger` constructor overloads.

## See also

- [Load from stream]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-stream.md" >}})
- [Load password-protected document]({{< ref "merger/python-net/developer-guide/loading-documents/load-password-protected.md" >}})
- [Get document information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}})
