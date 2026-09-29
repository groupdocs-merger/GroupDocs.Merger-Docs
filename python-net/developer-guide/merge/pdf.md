---
id: merge-pdf
url: merger/python-net/merge-pdf
title: Merge PDF
description: "Follow this guide and learn how to merge PDF files, combine several PDFs into one using GroupDocs.Merger for Python via .NET API and couple lines of code"
keywords: Merge PDF, Combine PDF, Join PDF, Merge PDF with GroupDocs.Merger for Python via .NET
productName: GroupDocs.Merger for Python via .NET
weight: 1
toc: True
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge PDF files in Python via .NET
    appDescription: Merge PDF in a quick and efficient way using Python via .NET language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PDF files in Python via .NET
        description: Learn how to merge PDF files in Python via .NET language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-net
        steps:
        - name: Load source PDF files
          text: Create an instance of Merger class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 159
          imageWidth: 603
        - name: Add other PDF files
          text: Add other PDF files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 159
          imageWidth: 603
        - name: Merge PDF files and save result
          text: Call Merger class Save method and pass the filename for the resultant PDF file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 159
          imageWidth: 603
---

GroupDocs.Merger for Python via .NET lets you combine multiple PDF documents into a single file programmatically. All text, images, tables, graphs, forms, and other content are preserved exactly as in the originals — no third-party software or manual work required.

## Steps to merge PDF files

1. Create an instance of the `Merger` class and pass the path to the first (base) PDF file.
2. Call `merger.join()` with the path to each additional PDF to append.
3. Call `merger.save()` with the desired output path to write the merged file.

{{< tabs "merge-pdf-example" >}}
{{< tab "merge_pdf_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_pdf_documents():
    # Load the first document as the merge base
    with Merger("./input.pdf") as merger:
        # Append the second PDF document
        merger.join("./input2.pdf")
        # Save the combined document
        merger.save("./output.pdf")

if __name__ == "__main__":
    merge_pdf_documents()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/pdf/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.pdf" >}}
{{< tab-text >}}
`input2.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/pdf/input2.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 252 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/pdf/merge_pdf_documents/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base document**: `Merger("./input.pdf")` opens the first PDF as the merge base inside a context manager, ensuring resources are released automatically.
- **Append second document**: `merger.join("./input2.pdf")` appends the content of the second PDF. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.pdf")` writes the merged PDF to disk.

## Merge PDF with bookmark options

Use `PdfJoinOptions` to control how PDF content is joined. For example, setting `use_bookmarks=True` preserves the source document bookmarks in the merged output.

{{< tabs "merge-pdf-bookmarks-example" >}}
{{< tab "merge_pdf_with_bookmarks.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import PdfJoinOptions

def merge_pdf_with_bookmarks():
    # Load the first document as the merge base
    with Merger("./input.pdf") as merger:
        # Configure join options to preserve bookmarks
        pdf_join_options = PdfJoinOptions()
        pdf_join_options.use_bookmarks = True
        # Append the second PDF document with bookmark options applied
        merger.join("./input2.pdf", pdf_join_options)
        # Save the combined document
        merger.save("./output.pdf")

if __name__ == "__main__":
    merge_pdf_with_bookmarks()
```
{{< /tab >}}
{{< tab "input.pdf" >}}
{{< tab-text >}}
`input.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/pdf/input.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.pdf" >}}
{{< tab-text >}}
`input2.pdf` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/pdf/input2.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pdf" >}}  
```text
Binary file (PDF, 252 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/pdf/merge_pdf_with_bookmarks/output.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **`PdfJoinOptions`**: Provides PDF-specific join settings.
- **`use_bookmarks = True`**: Instructs the merger to retain the document outline (bookmarks) from each source PDF so readers can navigate the merged result.

## About PDF File Format

Portable Document Format (PDF) is a type of document created by Adobe back in the 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware, and Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well as in most modern browsers like Chrome, Safari, and Firefox via extensions/plug-ins.

### Merge PDF Live Demo

GroupDocs.Merger for Python via .NET provides an online [**PDF Merger App**](https://products.groupdocs.app/merger/pdf), which allows you to try it for free and check its quality and accuracy.

[!["Merge PDF"](/merger/net/images/merge/merge-pdf.png)](https://products.groupdocs.app/merger/pdf)

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.
- [`PdfJoinOptions`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/pdfjoiptions/) — PDF-specific join settings.

## See also

- [Merge Word documents]({{< ref "merger/python-net/developer-guide/merge/word.md" >}})
- [Split a PDF document]({{< ref "merger/python-net/developer-guide/single-document-operations/split-document.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
