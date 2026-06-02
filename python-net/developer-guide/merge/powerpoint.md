---
id: merge-powerpoint
url: merger/python-net/merge/powerpoint
title: Merge PowerPoint Presentations
weight: 3
description: "This article demonstrates how to merge PowerPoint presentation files of PPT, PPTX, ODP and many other formats with a couple of Python via .NET code lines and GroupDocs.Merger for Python via .NET."
keywords: Merge Presentations, Merge PPT files, Merge PPTX files
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge PPTX files in Python via .NET
    appDescription: Merge PPTX in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge PPTX files in Python via .NET
        description: Learn how to merge PPTX files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source PPTX files
          text: Create an instance of Merger class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other PPTX files
          text: Add other PPTX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge PPTX files and save result
          text: Call Merger class Save method and pass the filename for the resultant PPTX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

GroupDocs.Merger for Python via .NET makes it easy to combine multiple PowerPoint presentations into a single file programmatically. All slides, shapes, animations, embedded media, and other content are preserved — no Microsoft PowerPoint or third-party desktop software required.

Common presentation file extensions include **PPTX**, **PPT**, **PPSX**, and **PPS**. PPTX is the default XML-based format introduced with Microsoft Office 2007; PPT is the older binary format supported by earlier versions of PowerPoint.

## Steps to merge PPTX files

1. Create an instance of the `Merger` class and pass the path to the first (base) PPTX file.
2. Call `merger.join()` with the path to each additional PPTX file to append.
3. Call `merger.save()` with the desired output path to write the merged file.

{{< tabs "merge-powerpoint-example" >}}
{{< tab "merge_powerpoint_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_powerpoint_documents():
    # Load the first presentation as the merge base
    with Merger("./input.pptx") as merger:
        # Append the second PowerPoint presentation
        merger.join("./input2.pptx")
        # Save the combined presentation
        merger.save("./output.pptx")

if __name__ == "__main__":
    merge_powerpoint_documents()
```
{{< /tab >}}
{{< tab "input.pptx" >}}
{{< tab-text >}}
`input.pptx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/powerpoint/input.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.pptx" >}}
{{< tab-text >}}
`input2.pptx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/powerpoint/input2.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.pptx" >}}  
```text
Binary file (PPTX, 88 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/powerpoint/merge_powerpoint_documents/output.pptx)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base document**: `Merger("./input.pptx")` opens the first presentation as the merge base inside a context manager.
- **Append second document**: `merger.join("./input2.pptx")` appends all slides from the second file. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.pptx")` writes the merged presentation to disk.

### Merge PowerPoint Live Demo

GroupDocs.Merger for Python via .NET provides an online [**PowerPoint Merger App**](https://products.groupdocs.app/merger/powerpoint), which allows you to try it for free and check its quality and accuracy.

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.

## See also

- [Merge Excel spreadsheets]({{< ref "merger/python-net/developer-guide/merge/excel.md" >}})
- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
