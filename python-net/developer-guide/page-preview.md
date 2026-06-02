---
id: page-preview
url: merger/python-net/developer-guide/page-preview
title: Generate Page Previews
linkTitle: Page Preview
weight: 3
description: "Rasterize document pages to PNG, JPEG, or BMP image files using generate_preview() and a file-stream callback with GroupDocs.Merger for Python via .NET."
keywords: page preview, generate preview, PNG preview, JPEG preview, BMP preview, PreviewOptions, PreviewMode, create_page_stream, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) can rasterize document pages to image files — PNG, JPEG, or BMP — using the `generate_preview()` method. You supply a callback function that receives the 1-based page number and returns an open writable file stream; the library renders each requested page and writes the result into that stream.

## Steps to generate page previews

1. Define a `create_page_stream` callback that accepts a page number and returns an open binary file object (e.g. `open(path, "wb")`).
2. Create a `PreviewOptions` instance, passing the callback, the desired `PreviewMode`, and a list of page numbers to render.
3. Instantiate the `Merger` class with the source document path.
4. Call `merger.generate_preview()` with the `PreviewOptions` object.

{{< tabs "page-preview-example" >}}
{{< tab "generate_page_previews.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import PreviewOptions, PreviewMode

def generate_page_previews():
    # Callback: called once per requested page; must return a writable FILE stream
    def create_page_stream(page_number):
        # Open a file for writing — do NOT return BytesIO here
        return open(f"./page-{page_number}.png", "wb")

    # Load the source document
    with Merger("./input.pdf") as merger:
        # Configure preview: PNG format, render pages 1 and 2
        preview_options = PreviewOptions(create_page_stream, PreviewMode.PNG, [1, 2])
        # Rasterize the requested pages and write them via the callback streams
        merger.generate_preview(preview_options)

if __name__ == "__main__":
    generate_page_previews()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/page-preview/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "generate-page-previews-outputs.zip" >}}  
```text
page-1.png (46 KB)
page-2.png (46 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/page-preview/generate_page_previews/generate-page-previews-outputs.zip)
{{< /tab >}}
{{< /tabs >}}

{{< alert style="info" >}}
**The callback must return a file/path stream, not `BytesIO`.**
A `BytesIO` object returned from the `create_page_stream` callback will come back empty — the .NET bridge does not write back into callback-provided in-memory streams. Always use `open(path, "wb")` or another operating-system file stream.

**Linux / macOS:** page rasterization requires **libgdiplus** (GDI+). Install it with `apt-get install libgdiplus` (Debian/Ubuntu) or `brew install mono-libgdiplus` (macOS/Homebrew) before calling `generate_preview()`.
{{< /alert >}}

### Explanation

- **Stream Callback**: `create_page_stream(page_number)` is invoked once for every page in the requested list. It must open and return a writable binary file handle. The library writes the rendered image data into that handle.
- **PreviewOptions**: The constructor accepts three arguments: the stream callback, a `PreviewMode` enum value (`PNG`, `JPEG`, or `BMP`), and a list of 1-based page numbers to render. Omit the page list to render all pages.
- **Load Document**: The `Merger` context manager opens the source document and releases all resources when the `with` block exits.
- **Generate**: `merger.generate_preview(preview_options)` rasterizes each requested page and writes the image into the corresponding stream returned by the callback.

After running the example, you will find `page-1.png` and `page-2.png` in the working directory.

Refer to the [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/python-net/) for full details on `PreviewOptions` and `PreviewMode`.

## See also

- [Get document information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}})
- [Get supported file types]({{< ref "merger/python-net/developer-guide/get-supported-file-types.md" >}})
