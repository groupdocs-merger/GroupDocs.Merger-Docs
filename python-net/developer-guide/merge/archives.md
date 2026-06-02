---
id: merge-archives
url: merger/python-net/merge/archives
title: Merge archives
description: "Learn how to merge archive files, combine archive files into one file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge archive files in Python via .NET, Combine archive files programmatically
productName: GroupDocs.Merger for Python via .NET
toc: True
weight: 15
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge archive files in Python via .NET
    appDescription: Merge archive in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge archive files in Python via .NET
        description: Learn how to merge archive files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source archive files
          text: Create an instance of Merger class and pass source archive file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other archive files
          text: Add other archive files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge archive files and save result
          text: Call Merger class Save method and pass the filename for the resultant archive file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

GroupDocs.Merger for Python via .NET allows you to combine multiple archive files into a single archive programmatically. The library supports common archive formats such as **ZIP** and **TAR** — no external compression tools required.

## Steps to merge ZIP archives

1. Create an instance of the `Merger` class and pass the path to the first (base) ZIP file.
2. Call `merger.join()` with the path to each additional ZIP file to append.
3. Call `merger.save()` with the desired output path to write the merged archive.

{{< tabs "merge-archives-example" >}}
{{< tab "merge_archive_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_archive_documents():
    # Load the first archive as the merge base
    with Merger("./input.zip") as merger:
        # Append the second archive
        merger.join("./input2.zip")
        # Save the combined archive
        merger.save("./output.zip")

if __name__ == "__main__":
    merge_archive_documents()
```
{{< /tab >}}
{{< tab "input.zip" >}}
{{< tab-text >}}
`input.zip` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/archives/input.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.zip" >}}
{{< tab-text >}}
`input2.zip` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/archives/input2.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.zip" >}}  
```text
Binary file (ZIP, 1 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/archives/merge_archive_documents/output.zip)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base archive**: `Merger("./input.zip")` opens the first ZIP archive as the merge base inside a context manager.
- **Append second archive**: `merger.join("./input2.zip")` appends all entries from the second archive. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.zip")` writes the merged archive to disk.

## Merge different archive file formats

- [How to merge archives to ZIP in Python via .NET]({{< ref "merger/python-net/getting-started/use-cases/how-to-merge-archives-to-zip-using-python-net.md" >}})

### Merge Archives Live Demo

GroupDocs.Merger for Python via .NET provides online [**ZIP Merger App**](https://products.groupdocs.app/merger/zip) and [**TAR Merger App**](https://products.groupdocs.app/merger/tar), which allow you to try them for free and check their quality and accuracy.

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.

## See also

- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [Get document information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
