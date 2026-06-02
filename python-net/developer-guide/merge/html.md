---
id: merge-html
url: merger/python-net/merge/html
title: Merge HTML
description: "Learn how to merge HTML files, combine HTML files into one file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge HTML files in Python via .NET, Combine HTML files programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 1
toc: True
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge HTML files in Python via .NET
    appDescription: Merge HTML in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge HTML files in Python via .NET
        description: Learn how to merge HTML files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source HTML files
          text: Create an instance of Merger class and pass source HTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other HTML files
          text: Add other HTML files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge HTML files and save result
          text: Call Merger class Save method and pass the filename for the resultant HTML file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

GroupDocs.Merger for Python via .NET allows you to combine multiple HTML files into a single document programmatically. All content — text, images, tables, embedded styles, and other markup — is preserved in the merged output.

HTML (HyperText Markup Language) is the standard language for web pages displayed in browsers. HTML 5, the latest version, offers broad flexibility for structuring and presenting content. HTML files can be served from a web server or loaded from the local file system.

## Steps to merge HTML files

1. Create an instance of the `Merger` class and pass the path to the first (base) HTML file.
2. Call `merger.join()` with the path to each additional HTML file to append.
3. Call `merger.save()` with the desired output path to write the merged file.

{{< tabs "merge-html-example" >}}
{{< tab "merge_html_documents.py" >}}
```python
from groupdocs.merger import Merger

def merge_html_documents():
    # Load the first HTML file as the merge base
    with Merger("./input.html") as merger:
        # Append the second HTML file
        merger.join("./input2.html")
        # Save the combined HTML file
        merger.save("./output.html")

if __name__ == "__main__":
    merge_html_documents()
```
{{< /tab >}}
{{< tab "input.html" >}}
{{< tab-text >}}
`input.html` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/html/input.html) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.html" >}}
{{< tab-text >}}
`input2.html` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/html/input2.html) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.html" >}}  
```text
<html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8" /><meta http-equiv="Content-Style-Type" content="text/css" /><meta name="generator" content="Aspose.Words for .NET 26.4.0" /><title></title></head><body style="font-family:'Times New Roman'; font-size:12pt"><div><p style="margin-top:0pt; margin-bottom:0pt"><a name="Bookmark1"><span>Text inside a bookmark 1</span></a></p><p style="margin-top:12pt; margin-bottom:3pt; page-break-after:avoid; font-size:16pt; -aw-outline-l
[TRUNCATED]
```
[Download full output](/merger/python-net/_output_files/developer-guide/merge/html/merge_html_documents/output.html)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base document**: `Merger("./input.html")` opens the first HTML file as the merge base inside a context manager.
- **Append second document**: `merger.join("./input2.html")` appends the content of the second file. Call `join` again for each additional file.
- **Save result**: `merger.save("./output.html")` writes the merged HTML to disk.

### Merge HTML Live Demo

GroupDocs.Merger for Python via .NET provides an online [**HTML Merger App**](https://products.groupdocs.app/merger/html), which allows you to try it for free and check its quality and accuracy.

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.

## See also

- [Merge EPUB files]({{< ref "merger/python-net/developer-guide/merge/epub.md" >}})
- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
