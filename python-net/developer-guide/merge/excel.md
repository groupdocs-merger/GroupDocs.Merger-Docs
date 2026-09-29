---
id: merge-excel
url: merger/python-net/merge/excel
title: Merge Excel spreadsheets
linkTitle: Merge Excel
weight: 4
description: "Follow this guide and learn how to merge MS Excel spreadsheets using Python via .NET programming language."
keywords: Merge Excel files, Merge Spreadsheets, Merge XLS, Merge XLSX
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge XLSX files in Python via .NET
    appDescription: Merge XLSX in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge XLSX in Python via .NET
        description: Learn how to merge XLSX in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source XLSX files
          text: Create an instance of Merger class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other XLSX files
          text: Add other XLSX files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge XLSX files and save result
          text: Call Merger class Save method and pass the filename for the resultant XLSX file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

GroupDocs.Merger for Python via .NET allows you to combine multiple Excel spreadsheets into a single file programmatically. All worksheets, data, formulas, charts, and formatting are preserved — no Microsoft Excel or third-party software required.

Spreadsheet files store data in rows and columns and are saved in formats such as **XLSX** (Microsoft Excel Open XML Spreadsheet), **XLS** (Microsoft Excel Binary File Format), and **ODS** (OpenDocument Spreadsheet). XLSX is the default format introduced with Microsoft Office 2007, based on the Open Packaging Conventions (OOXML/ECMA-376 standard).

## Steps to merge XLSX files

1. Create an instance of the `Merger` class and pass the path to the first (base) XLSX file.
2. Call `merger.join()` with the path to each additional XLSX file to append.
3. Call `merger.save()` with the desired output path to write the merged file.

{{< tabs "merge-excel-example" >}}
{{< tab "merge_excel_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_excel_documents():
    # Load the first document as the merge base
    with Merger("./input.xlsx") as merger:
        # Append the second Excel spreadsheet
        merger.join("./input2.xlsx")
        # Save the combined document
        merger.save("./output.xlsx")

if __name__ == "__main__":
    merge_excel_documents()
```
{{< /tab >}}
{{< tab "input.xlsx" >}}
{{< tab-text >}}
`input.xlsx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/excel/input.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.xlsx" >}}
{{< tab-text >}}
`input2.xlsx` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/excel/input2.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.xlsx" >}}  
```text
Binary file (XLSX, 18 KB)
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/excel/merge_excel_documents/output.xlsx)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base document**: `Merger("./input.xlsx")` opens the first Excel spreadsheet as the merge base inside a context manager.
- **Append second document**: `merger.join("./input2.xlsx")` appends all worksheets from the second file. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.xlsx")` writes the merged spreadsheet to disk.

### Merge XLSX Live Demo

GroupDocs.Merger for Python via .NET provides an online [**XLSX Merger App**](https://products.groupdocs.app/merger/xlsx), which allows you to try it for free and check its quality and accuracy.

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.

## See also

- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [Merge PowerPoint presentations]({{< ref "merger/python-net/developer-guide/merge/powerpoint.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
