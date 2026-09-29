---
id: rotate-pages
url: merger/python-net/rotate-pages
title: Rotate pages
linkTitle: Rotate pages
weight: 8
description: "Following this guide you will learn how to change PDF document page rotation angle using GroupDocs.Merger for Python via .NET API."
keywords: Rotate PDF pages, Rotate document pages, Change PDF page rotation angle, RotateOptions, RotateMode, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you rotate specific pages (or all pages) in a PDF document by 90, 180, or 270 degrees. The rotation is configured through [RotateOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rotateoptions/) and applied with `merger.rotate()`.

Here are the steps to rotate document pages:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source document.
- Create a [RotateOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rotateoptions/) object with the desired [RotateMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rotatemode/) and the list of 1-based page numbers to rotate.
- Call `merger.rotate()` passing the `RotateOptions` object.
- Call `merger.save()` to write the resulting document.

{{< tabs "rotate-pages-example" >}}
{{< tab "rotate_pages.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import RotateOptions, RotateMode

def rotate_document_pages():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Rotate pages 1 and 2 by 90 degrees clockwise
        # Pass page numbers as a list — positional integer arguments are not supported
        merger.rotate(RotateOptions(RotateMode.ROTATE90, [1, 2]))
        # Save the document with the rotated pages
        merger.save("./output.pdf")

if __name__ == "__main__":
    rotate_document_pages()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/rotate-pages/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 337 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/rotate-pages/rotate_document_pages/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source document**: `Merger("./input.pdf")` opens the document as a context manager, ensuring resources are released on exit.
- **`RotateOptions(RotateMode.ROTATE90, [1, 2])`**: the first argument is the rotation angle enum; the second argument is a **list** of 1-based page numbers. Available modes are `RotateMode.ROTATE90`, `RotateMode.ROTATE180`, and `RotateMode.ROTATE270`.
- **Page numbers must be a list**: `RotateOptions(RotateMode.ROTATE90, [1, 2])` is correct. Passing integers positionally — `RotateOptions(mode, 1, 2)` — is not supported and raises a runtime error.
- **`merger.rotate()`**: the correct Python method name. The old method name `rotate_pages` does not exist and must not be used.
- **`merger.save("./output.pdf")`**: writes the resulting document with the pages at their new rotation angles.

{{< alert style="tip" >}}
Rotation is cumulative across multiple calls within the same `Merger` session. To rotate different pages by different angles, call `merger.rotate()` once per angle before calling `merger.save()`.
{{< /alert >}}

### API reference

- [RotateOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rotateoptions/)
- [RotateMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rotatemode/)
- [Merger.rotate()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Change page orientation]({{< ref "merger/python-net/developer-guide/single-document-operations/change-page-orientation" >}})
- [Move page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page" >}})
- [Swap pages]({{< ref "merger/python-net/developer-guide/single-document-operations/swap-pages" >}})
