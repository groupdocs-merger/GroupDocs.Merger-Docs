---
id: change-page-orientation
url: merger/python-net/change-page-orientation
title: Change page orientation
linkTitle: Change page orientation
weight: 7
description: "Following this guide you will learn how to change Word document page orientation to Portrait or Landscape using GroupDocs.Merger for Python via .NET."
keywords: DOCX page orientation, Change Word page orientation, Page Portrait orientation, Page Landscape orientation, OrientationOptions, OrientationMode, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you set **Portrait** or **Landscape** orientation for specific pages (or all pages) of a Word document. The orientation is configured through [OrientationOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/orientationoptions/) and applied with `merger.change_orientation()`.

Here are the steps to change the page orientation:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source document.
- Create an [OrientationOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/orientationoptions/) object with the desired [OrientationMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/orientationmode/) and the list of 1-based page numbers to change.
- Call `merger.change_orientation()` passing the `OrientationOptions` object.
- Call `merger.save()` to write the resulting document.

{{< tabs "change-page-orientation-example" >}}
{{< tab "change_page_orientation.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import OrientationOptions, OrientationMode

def change_page_orientation():
    # Load the source Word document
    with Merger("./input.pdf") as merger:
        # Set pages 1 and 2 to Landscape orientation
        merger.change_orientation(OrientationOptions(OrientationMode.LANDSCAPE, [1, 2]))
        # Save the document with the updated page orientations
        merger.save("./output.pdf")

if __name__ == "__main__":
    change_page_orientation()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/change-page-orientation/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 336 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/change-page-orientation/change_page_orientation/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source document**: `Merger("./input.pdf")` opens the document as a context manager, ensuring resources are released on exit.
- **`OrientationOptions(OrientationMode.LANDSCAPE, [1, 2])`**: the first argument is the orientation enum; the second argument is a **list** of 1-based page numbers. Use `OrientationMode.LANDSCAPE` or `OrientationMode.PORTRAIT`.
- **`merger.change_orientation()`**: the correct Python method name. Do not use `merger.orientation()` — that method does not exist.
- **`merger.save("./output.pdf")`**: writes the document with the updated page orientations to the specified path.

{{< alert style="tip" >}}
Page orientation changes are primarily meaningful for word-processing formats such as DOCX and DOC. Using `change_orientation()` on PDF files rewrites the page layout; for visual rotation of PDF page content, use [Rotate pages]({{< ref "merger/python-net/developer-guide/single-document-operations/rotate-pages" >}}) instead.
{{< /alert >}}

### API reference

- [OrientationOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/orientationoptions/)
- [OrientationMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/orientationmode/)
- [Merger.change_orientation()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Rotate pages]({{< ref "merger/python-net/developer-guide/single-document-operations/rotate-pages" >}})
- [Move page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page" >}})
- [Swap pages]({{< ref "merger/python-net/developer-guide/single-document-operations/swap-pages" >}})
