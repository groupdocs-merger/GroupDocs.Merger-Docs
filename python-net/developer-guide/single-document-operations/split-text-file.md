---
id: split-text-file
url: merger/python-net/split-text-file
title: Split text file
linkTitle: Split text file
weight: 4
description: "Follow this guide and learn how to split a text file into several resultant files by line numbers using GroupDocs.Merger for Python via .NET API."
keywords: Split file, Split text file, Split text by line number, TextSplitOptions, TextSplitMode, GroupDocs.Merger, Python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

[**GroupDocs.Merger for Python via .NET**](https://products.groupdocs.com/merger/python-net) lets you split a plain-text file into multiple output files based on line numbers. You can extract specific lines (one output per listed line) or split at line boundaries to produce multi-line segments — all controlled through [TextSplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/textsplitoptionsoptions/).

Here are the steps to split a text file:

- Instantiate [Merger](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) with the path to the source `.txt` file.
- Create a [TextSplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/textsplitoptionsoptions/) object using **keyword arguments** — `file_path_format`, `line_numbers`, and `mode`.
- Call `merger.split()` passing the `TextSplitOptions` object.

{{< alert style="warning" >}}
`TextSplitOptions` must be constructed with keyword arguments. Passing arguments positionally will fail at runtime.
{{< /alert >}}

{{< tabs "split-text-file-example" >}}
{{< tab "split_text_file.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain.options import TextSplitOptions, TextSplitMode

def split_text_file_by_lines():
    # Load the source text file
    with Merger("./input.txt") as merger:
        # Split at lines 2 and 4 — each listed line becomes a separate output file
        # Output files: lines_0.txt (line 2), lines_1.txt (line 4)
        # IMPORTANT: use keyword arguments — positional arguments will fail
        merger.split(TextSplitOptions(
            file_path_format="./lines_{0}.txt",
            line_numbers=[2, 4],
            mode=TextSplitMode.LINES,
        ))

def split_text_file_by_interval():
    # Load the source text file
    with Merger("./input.txt") as merger:
        # Split at line boundaries [2, 4] using INTERVAL mode
        # lines_0.txt → line 1, lines_1.txt → lines 2-3, lines_2.txt → lines 4+
        merger.split(TextSplitOptions(
            file_path_format="./lines_{0}.txt",
            line_numbers=[2, 4],
            mode=TextSplitMode.INTERVAL,
        ))

if __name__ == "__main__":
    split_text_file_by_lines()
    split_text_file_by_interval()
```
{{< /tab >}}
{{< tab "input.txt" >}}
{{< tab-text >}}
`input.txt` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/single-document-operations/split-text-file/input.txt) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "split-text-file-by-lines-outputs.zip" >}}  
```text
lines_0.txt (36 bytes)
lines_1.txt (67 bytes)
lines_2.txt (98 bytes)
```
[Download full output](/merger/python-net/_output_files/developer-guide/single-document-operations/split-text-file/split_text_file_by_lines/split-text-file-by-lines-outputs.zip)
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load source file**: `Merger("./input.txt")` opens the text file as a context manager.
- **`TextSplitMode.LINES`**: each number in `line_numbers` identifies a single line to extract. The result is one output file per listed line number.
- **`TextSplitMode.INTERVAL`**: the listed numbers are treated as boundary points. Lines before the first boundary form the first segment, lines between each pair of boundaries form subsequent segments, and lines after the last boundary form the final segment.
- **Keyword arguments**: `file_path_format`, `line_numbers`, and `mode` must always be passed as keyword arguments to `TextSplitOptions`. Positional usage is not supported and raises a runtime error.
- **Output format**: `{0}` in the path format is replaced with a zero-based index for each output file.
- No explicit `merger.save()` call is needed — `split()` writes the output files directly.

### API reference

- [TextSplitOptions](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/textsplitoptionsoptions/)
- [TextSplitMode](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/textsplitmode/)
- [Merger.split()](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/)

### See also

- [Split document]({{< ref "merger/python-net/developer-guide/single-document-operations/split-document" >}})
- [Extract pages]({{< ref "merger/python-net/developer-guide/single-document-operations/extract-pages" >}})
