---
id: word
url: merger/python-net/merge/word
title: Merge Word documents
linkTitle: Merge Word documents
description: "Follow this guide and learn how to merge Word documents, combine several DOCX or DOC files into one using GroupDocs.Merger for Python via .NET."
keywords: Merge Word, Merge DOCX, Merge DOC, Join DOCX, Combine DOC with GroupDocs.Merger for Python via .NET
productName: GroupDocs.Merger for Python via .NET
weight: 2
hideChildren: True
toc: True
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge DOC files in Python via .NET
    appDescription: Merge DOC in a quick and efficient way using Python via .NET language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge DOC files in Python via .NET
        description: Learn how to merge DOC files in Python via .NET language and GroupDocs.Merger for .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-net
        steps:
        - name: Load source DOC files
          text: Create an instance of Merger class and pass source DOC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 159
          imageWidth: 603
        - name: Add other DOC files
          text: Add other DOC files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 159
          imageWidth: 603
        - name: Merge DOC files and save result
          text: Call Merger class Save method and pass the filename for the resultant DOC file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 159
          imageWidth: 603
---

GroupDocs.Merger for Python via .NET makes it straightforward to combine multiple Word processing documents — DOCX, DOC, RTF, and others — into a single file. All formatting, styles, images, tables, and other content are preserved without requiring Microsoft Word or any other desktop software.

Word processing files range from plain-text formats (**TXT**, **CSV**) to rich-text formats such as **DOCX**, **DOC**, and **RTF** that support full font, paragraph, and page formatting.

## Steps to merge DOCX documents

1. Create an instance of the `Merger` class and pass the path to the first (base) DOCX file.
2. Call `merger.join()` with the path to each additional DOCX file to append.
3. Call `merger.save()` with the desired output path to write the merged file.

{{< tabs "merge-word-example" >}}
{{< tab "merge_word_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_word_documents():
    # Load the first document as the merge base
    with Merger("./input.docx") as merger:
        # Append the second Word document
        merger.join("./input2.docx")
        # Save the combined document
        merger.save("./output.docx")

if __name__ == "__main__":
    merge_word_documents()
```
{{< /tab >}}
{{< tab "input.docx" >}}
{{< tab-text >}}
`input.docx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/word/input.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.docx" >}}
{{< tab-text >}}
`input2.docx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/word/input2.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.docx" >}}  
```text
Binary file (DOCX, 8 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/word/merge_word_documents/output.docx)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base document**: `Merger("./input.docx")` opens the first DOCX file as the merge base inside a context manager.
- **Append second document**: `merger.join("./input2.docx")` appends the content of the second file. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.docx")` writes the merged document to disk.

## Merge Word documents in continuous mode

Use `WordJoinOptions` with `WordJoinMode.CONTINUOUS` to join documents without inserting a page break between them — the second document flows on directly after the last paragraph of the first.

{{< tabs "merge-word-continuous-example" >}}
{{< tab "merge_word_documents_continuous.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import WordJoinOptions, WordJoinMode

def merge_word_documents_continuous():
    # Load the first document as the merge base
    with Merger("./input.docx") as merger:
        # Configure join options for continuous (no page break) merging
        word_join_options = WordJoinOptions()
        word_join_options.mode = WordJoinMode.CONTINUOUS
        # Append the second document in continuous mode
        merger.join("./input2.docx", word_join_options)
        # Save the combined document
        merger.save("./output.docx")

if __name__ == "__main__":
    merge_word_documents_continuous()
```
{{< /tab >}}
{{< tab "input.docx" >}}
{{< tab-text >}}
`input.docx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/word/input.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.docx" >}}
{{< tab-text >}}
`input2.docx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/word/input2.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.docx" >}}  
```text
Binary file (DOCX, 8 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/word/merge_word_documents_continuous/output.docx)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **`WordJoinOptions`**: Provides Word-specific join settings.
- **`WordJoinMode.CONTINUOUS`**: The appended document starts immediately after the last content of the preceding document rather than on a new page.

### Merge Word files Live Demo

GroupDocs.Merger for Python via .NET provides an online [**Word Merger App**](https://products.groupdocs.app/merger/word), which allows you to try it for free and check its quality and accuracy.

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.
- [`WordJoinOptions`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/wordjoiptions/) — Word-specific join settings.
- [`WordJoinMode`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/wordjoinmode/) — enum: `CONTINUOUS`, and others.

## See also

- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [Merge text files]({{< ref "merger/python-net/developer-guide/merge/text.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
