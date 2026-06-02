---
id: move-page
url: merger/python-net/move-page
title: Move page
linkTitle: Move page
weight: 1
description: "This article demonstrates how to move a document page to a new position within PDF, Word, Excel, PowerPoint and other document types using GroupDocs.Merger for Python via .NET API."
keywords: Move document page, Move PDF page, Move Word document page, Move page to another position, MoveOptions, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you relocate any page to a different position within a document. All other pages shift to accommodate the move. The operation is configured through [MoveOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/moveoptions/).

Here are the steps to move a document page:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source document.
- Create a [MoveOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/moveoptions/) object specifying the current page number and the target position.
- Call `merger.move_page()` passing the `MoveOptions` object.
- Call `merger.save()` to write the resulting document.

{{< tabs "move-page-example" >}}
{{< tab "move_page.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import MoveOptions

def move_document_page():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Move page 4 to position 1 (the beginning of the document)
        merger.move_page(MoveOptions(4, 1))
        # Save the document with the updated page order
        merger.save("./output.pdf")

if __name__ == "__main__":
    move_document_page()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/move-page/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 418 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/move-page/move_document_page/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source document**: `Merger("./input.pdf")` opens the document as a context manager, ensuring resources are released on exit.
- **`MoveOptions(4, 1)`**: the first argument is the current 1-based page number to move; the second argument is the 1-based target position. In this example, page 4 is inserted at position 1, pushing the original pages 1–3 forward by one.
- **`merger.move_page()`**: the correct Python method name (singular). The equivalent .NET method is `MovePage`.
- **`merger.save("./output.pdf")`**: writes the resulting document with the page in its new position.

{{< alert style="tip" >}}
To exchange the positions of two pages rather than inserting one at a new position, use [Swap pages]({{< ref "merger/python-net/developer-guide/single-document-operations/swap-pages" >}}) instead.
{{< /alert >}}

### API reference

- [MoveOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/moveoptions/)
- [Merger.move_page()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Swap pages]({{< ref "merger/python-net/developer-guide/single-document-operations/swap-pages" >}})
- [Remove pages]({{< ref "merger/python-net/developer-guide/single-document-operations/remove-pages" >}})
- [Extract pages]({{< ref "merger/python-net/developer-guide/single-document-operations/extract-pages" >}})
