---
id: merge-txt
url: merger/python-net/merge/txt
title: Merge text files
description: "Learn how to merge TXT files, combine TXT files into one file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge TXT files in Python via .NET, Combine TXT files programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 8
toc: True
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge TXT files in Python via .NET
    appDescription: Merge TXT in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge TXT files in Python via .NET
        description: Learn how to merge TXT files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source TXT files
          text: Create an instance of Merger class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other TXT files
          text: Add other TXT files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge TXT files and save result
          text: Call Merger class Save method and pass the filename for the resultant TXT file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

GroupDocs.Merger for Python via .NET makes it easy to combine multiple plain-text files into a single TXT file programmatically. No third-party software or text editor is required.

A file with the `.TXT` extension represents a text document that contains plain text organized in lines. Paragraphs are recognized by carriage returns, and the content is human-readable as a sequence of characters. Standard text documents can be opened in any text editor or word processing application on any operating system.

## Steps to merge TXT files

1. Create an instance of the `Merger` class and pass the path to the first (base) TXT file.
2. Call `merger.join()` with the path to each additional TXT file to append.
3. Call `merger.save()` with the desired output path to write the merged file.

{{< tabs "merge-text-example" >}}
{{< tab "merge_text_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_text_documents():
    # Load the first text file as the merge base
    with Merger("./input.txt") as merger:
        # Append the second text file
        merger.join("./input2.txt")
        # Save the combined text file
        merger.save("./output.txt")

if __name__ == "__main__":
    merge_text_documents()
```
{{< /tab >}}
{{< tab "input.txt" >}}
{{< tab-text >}}
`input.txt` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/text/input.txt) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.txt" >}}
{{< tab-text >}}
`input2.txt` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/text/input2.txt) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.txt" >}}  
```text
﻿EXAMPLE 1 EXAMPLE 1 EXAMPLE 1
EXAMPLE 2 EXAMPLE 2 EXAMPLE 2
EXAMPLE 3 EXAMPLE 3 EXAMPLE 3
EXAMPLE 4 EXAMPLE 4 EXAMPLE 4
EXAMPLE 5 EXAMPLE 5 EXAMPLE 5
EXAMPLE 6 EXAMPLE 6 EXAMPLE 6
EXAMPLE 1 EXAMPLE 1 EXAMPLE 1
EXAMPLE 2 EXAMPLE 2 EXAMPLE 2
EXAMPLE 3 EXAMPLE 3 EXAMPLE 3
EXAMPLE 4 EXAMPLE 4 EXAMPLE 4
[TRUNCATED]
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/text/merge_text_documents/output.txt)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base document**: `Merger("./input.txt")` opens the first text file as the merge base inside a context manager.
- **Append second document**: `merger.join("./input2.txt")` appends the content of the second file. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.txt")` writes the merged text to disk.

### Merge TXT Live Demo

GroupDocs.Merger for Python via .NET provides an online [**TXT Merger App**](https://products.groupdocs.app/merger/txt), which allows you to try it for free and check its quality and accuracy.

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.

## See also

- [Merge Word documents]({{< ref "merger/python-net/developer-guide/merge/word.md" >}})
- [Split a text file]({{< ref "merger/python-net/developer-guide/single-document-operations/split-text-file.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
