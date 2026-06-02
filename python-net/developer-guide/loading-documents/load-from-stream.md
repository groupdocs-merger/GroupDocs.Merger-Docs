---
id: load-from-stream
url: merger/python-net/developer-guide/loading-documents/load-from-stream
title: Load Document from Stream
linkTitle: Load From Stream
weight: 2
description: "Pass any Python binary file-like object to the Merger constructor to load and process documents directly from memory or any storage source with GroupDocs.Merger for Python via .NET."
keywords: load from stream, file stream, binary stream, open file handle, Merger constructor, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) accepts any readable binary stream as the source document. This lets you load documents from memory, network responses, cloud storage SDKs, or any other source that exposes a file-like object — without first writing the content to disk.

The `Merger` class provides the following stream-based constructor overloads:

- `Merger(stream)` — load from a binary readable stream with default settings.
- `Merger(stream, load_options)` — load from a stream and supply additional loading options (e.g. a password).
- `Merger(stream, load_options, settings)` — load from a stream with load options and custom `MergerSettings`.

{{< alert style="tip" >}}
GroupDocs.Merger accesses the stream only when an action (e.g. `join()`, `save()`) is performed on the `Merger` instance. Keep the stream open until the `with` block exits.
{{< /alert >}}

The following example demonstrates loading two PDF documents from binary file handles, merging them, and saving the result to disk:

{{< tabs "load-from-stream-example" >}}
{{< tab "load_from_stream.py" >}}
```python
from groupdocs.merger import Merger

def load_from_stream():
    # Open the base document as a binary stream
    with open("./input.pdf", "rb") as f:
        # Load the document directly from the stream
        with Merger(f) as merger:
            # Append a second document by file path
            merger.join("./input2.pdf")
            # Save the merged result to disk
            merger.save("./output.pdf")

if __name__ == "__main__":
    load_from_stream()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/loading-documents/load-from-stream/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.pdf" >}}
{{< tab-text >}}
`input2.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/loading-documents/load-from-stream/input2.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 252 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/loading-documents/load-from-stream/load_from_stream/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Open Stream**: `open("./input.pdf", "rb")` opens the base document as a binary readable file object. Any binary stream (e.g. `io.BytesIO`, an S3 response body, a `requests` response with `raw`) is accepted.
- **Load from Stream**: `Merger(f)` initialises the instance using the supplied stream. The stream must remain open until all operations are complete.
- **Join Additional Document**: `merger.join("./input2.pdf")` appends a second document specified by file path. You can also pass a stream here.
- **Save Result**: `merger.save("./output.pdf")` writes the combined document to disk. You can alternatively pass a writable stream to `save()`.
- **Resource Cleanup**: The nested `with` blocks ensure the `Merger` instance is disposed first, then the file handle is closed.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on stream-based constructor overloads.

## See also

- [Load from local disk]({{< ref "merger/python-net/developer-guide/loading-documents/load-from-local-disk.md" >}})
- [Load password-protected document]({{< ref "merger/python-net/developer-guide/loading-documents/load-password-protected.md" >}})
- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
