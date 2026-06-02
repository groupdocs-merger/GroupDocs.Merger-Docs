---
id: remove-pages
url: merger/python-net/remove-pages
title: Remove pages
linkTitle: Remove pages
weight: 2
description: "Follow this guide and learn how to remove pages from PDF or Word documents, delete worksheets from Excel files, or remove slides from PowerPoint presentations with GroupDocs.Merger for Python via .NET API."
keywords: Remove page from document, Delete page from document, Remove page, Delete page, RemoveOptions, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you remove one or more pages from a source document and save the result as a new document. The pages to delete are specified through [RemoveOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/removeoptions/).

Here are the steps to remove document pages:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source document.
- Create a [RemoveOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/removeoptions/) object with the list of 1-based page numbers to remove.
- Call `merger.remove_pages()` passing the `RemoveOptions` object.
- Call `merger.save()` to write the resulting document.

{{< tabs "remove-pages-example" >}}
{{< tab "remove_pages.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import RemoveOptions

def remove_document_pages():
    # Load the source PDF document
    with Merger("./input.pdf") as merger:
        # Remove page 2 from the document
        merger.remove_pages(RemoveOptions([2]))
        # Save the document with the specified page removed
        merger.save("./output.pdf")

if __name__ == "__main__":
    remove_document_pages()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/remove-pages/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 335 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/remove-pages/remove_document_pages/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source document**: `Merger("./input.pdf")` opens the document as a context manager, ensuring resources are released on exit.
- **`RemoveOptions([2])`**: accepts a list of 1-based page numbers to remove. To remove multiple pages, include them all in the list — for example, `RemoveOptions([2, 4, 6])`.
- **`merger.remove_pages()`**: applies the removal in memory. The original file is not modified.
- **`merger.save("./output.pdf")`**: writes the resulting document (with the specified pages omitted) to the given path.

{{< alert style="tip" >}}
To delete pages in a range (for example, all even pages from 1 to 10), use the `RemoveOptions` overload that accepts `start_number`, `end_number`, and a `RangeMode` value.
{{< /alert >}}

### API reference

- [RemoveOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/removeoptions/)
- [RangeMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/rangemode/)
- [Merger.remove_pages()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Extract pages]({{< ref "merger/python-net/developer-guide/single-document-operations/extract-pages" >}})
- [Move page]({{< ref "merger/python-net/developer-guide/single-document-operations/move-page" >}})
- [Swap pages]({{< ref "merger/python-net/developer-guide/single-document-operations/swap-pages" >}})
