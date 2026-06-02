---
id: merge-epub
url: merger/python-net/merge/epub
title: Merge EPUB
description: "Learn how to merge EPUB files, combine EPUB files into one file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge EPUB files in Python via .NET, Combine EPUB files programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 23
toc: True
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge EPUB files in Python via .NET
    appDescription: Merge EPUB in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge EPUB files in Python via .NET
        description: Learn how to merge EPUB files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source EPUB files
          text: Create an instance of Merger class and pass source EPUB file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other EPUB files
          text: Add other EPUB files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge EPUB files and save result
          text: Call Merger class Save method and pass the filename for the resultant EPUB file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

GroupDocs.Merger for Python via .NET allows you to combine multiple EPUB e-book files into a single file programmatically. All content from the source files is preserved in the merged output — no third-party e-reader software required.

## Steps to merge EPUB files

1. Create an instance of the `Merger` class and pass the path to the first (base) EPUB file.
2. Call `merger.join()` with the path to each additional EPUB file to append.
3. Call `merger.save()` with the desired output path to write the merged file.

{{< tabs "merge-epub-example" >}}
{{< tab "merge_epub_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_epub_documents():
    # Load the first EPUB file as the merge base
    with Merger("./input.epub") as merger:
        # Append the second EPUB file
        merger.join("./input2.epub")
        # Save the combined EPUB file
        merger.save("./output.epub")

if __name__ == "__main__":
    merge_epub_documents()
```
{{< /tab >}}
{{< tab "input.epub" >}}
{{< tab-text >}}
`input.epub` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/epub/input.epub) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.epub" >}}
{{< tab-text >}}
`input2.epub` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/epub/input2.epub) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.epub" >}}  
```text
Binary file (EPUB, 49 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/epub/merge_epub_documents/output.epub)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base document**: `Merger("./input.epub")` opens the first EPUB file as the merge base inside a context manager.
- **Append second document**: `merger.join("./input2.epub")` appends the content of the second file. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.epub")` writes the merged EPUB to disk.

## About EPUB File Format

Files with the `.EPUB` extension are an e-book file format that provides a standard for digital publications accepted by publishers and consumers worldwide. The format is supported by many e-readers and software applications. On macOS, the pre-installed Books app can open EPUB files directly. Compatible software is also widely available for smartphones, tablets, and desktop computers.

### Merge EPUB Live Demo

GroupDocs.Merger for Python via .NET provides an online [**EPUB Merger App**](https://products.groupdocs.app/merger/epub), which allows you to try it for free and check its quality and accuracy.

[!["Merge EPUB"](/merger/net/images/merge/merge-epub.png)](https://products.groupdocs.app/merger/epub)

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.

## See also

- [Merge HTML files]({{< ref "merger/python-net/developer-guide/merge/html.md" >}})
- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
