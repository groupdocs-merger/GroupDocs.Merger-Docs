---
id: merge-images
url: merger/python-net/merge/images
title: Merge images
description: "Learn how to merge image files, combine image files into one file programmatically in Python via .NET language using GroupDocs.Merger for Python via .NET library."
keywords: Merge image files in Python via .NET, Combine image files programmatically
productName: GroupDocs.Merger for Python via .NET
weight: 1
toc: True
hideChildren: False
structuredData:
    productCode: merger
    productPlatform: python-net
    appName: Merge image files in Python via .NET
    appDescription: Merge image in a quick and efficient way using Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
    howTo:
        name: How to merge image files in Python via .NET
        description: Learn how to merge image files in Python via .NET language and GroupDocs.Merger for Python via .NET API, without the use of any third-party software like Microsoft or Open Office.
        url: merger/python-net/merge/[TRGT_LWR]/#how-to-merge-[TRGT_LWR]-files-in-python-net
        steps:
        - name: Load source image files
          text: Create an instance of Merger class and pass source image file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
          imageUrl: merger/net/images/merge-files-step-1.png
          imageHeight: 157
          imageWidth: 645
        - name: Add other image files
          text: Add other image files you want to merge into a single document with Join method of Merger class.
          imageUrl: merger/net/images/merge-files-step-2.png
          imageHeight: 144
          imageWidth: 603
        - name: Merge image files and save result
          text: Call Merger class Save method and pass the filename for the resultant image file as parameter.
          imageUrl: merger/net/images/merge-files-step-3.png
          imageHeight: 151
          imageWidth: 646
---

GroupDocs.Merger for Python via .NET allows you to stack multiple images into a single output image programmatically. Use `ImageJoinOptions` to control the output format and the direction in which images are joined — horizontally side by side or vertically one above the other.

The library supports JPG, PNG, BMP, and other common image formats.

## Steps to merge JPEG images vertically

1. Create an instance of the `Merger` class and pass the path to the first (base) image.
2. Create an `ImageJoinOptions` instance specifying the target `FileType` and the `ImageJoinMode`.
3. Call `merger.join()` with the path to each additional image and the join options.
4. Call `merger.save()` with the desired output path.

{{< tabs "merge-images-example" >}}
{{< tab "merge_image_documents.py" >}}
```python
from groupdocs.merger import Merger
from groupdocs.merger.domain import FileType
from groupdocs.merger.domain.options import ImageJoinOptions, ImageJoinMode

def merge_image_documents():
    # Load the first image as the merge base
    with Merger("./input.jpg") as merger:
        # Configure join options: output as JPEG, stack images vertically
        image_join_options = ImageJoinOptions(FileType.JPEG, ImageJoinMode.VERTICAL)
        # Append the second image with the join options applied
        merger.join("./input2.jpg", image_join_options)
        # Save the combined image
        merger.save("./output.jpg")

if __name__ == "__main__":
    merge_image_documents()
```
{{< /tab >}}
{{< tab "input.jpg" >}}
{{< tab-text >}}
`input.jpg` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/images/input.jpg) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "input2.jpg" >}}
{{< tab-text >}}
`input2.jpg` is a sample file used in this example. Click [here](/merger/python-net/_sample_files/developer-guide/merge/images/input2.jpg) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Load base image**: `Merger("./input.jpg")` opens the first image as the merge base inside a context manager.
- **`ImageJoinOptions(FileType.JPEG, ImageJoinMode.VERTICAL)`**: Specifies that the output should be a JPEG file and that images should be stacked vertically (top to bottom). Use `ImageJoinMode.HORIZONTAL` to place them side by side instead.
- **Append second image**: `merger.join("./input2.jpg", image_join_options)` appends the second image according to the join options.
- **Save result**: `merger.save("./output.jpg")` writes the merged image to disk.

## Merge different image file formats

- [How to merge JPG images in Python via .NET]({{< ref "merger/python-net/getting-started/use-cases/how-to-merge-jpg-images-using-python-net.md" >}})
- [How to merge PNG images in Python via .NET]({{< ref "merger/python-net/getting-started/use-cases/how-to-merge-png-images-using-python-net.md" >}})
- [How to merge BMP images in Python via .NET]({{< ref "merger/python-net/getting-started/use-cases/how-to-merge-bmp-images-using-python-net.md" >}})

### Merge Images Live Demo

GroupDocs.Merger offers the following free online tools to test its quality and accuracy:

- [**JPG Merger App**](https://products.groupdocs.app/merger/jpg)
- [**PNG Merger App**](https://products.groupdocs.app/merger/png)
- [**BMP Merger App**](https://products.groupdocs.app/merger/bmp)

## API reference

- [`Merger`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger/merger/) — main class; `join`, `save` methods.
- [`ImageJoinOptions`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/imagejoinoptions/) — image-specific join settings.
- [`ImageJoinMode`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain.options/imagejoinmode/) — enum: `HORIZONTAL`, `VERTICAL`.
- [`FileType`](https://reference.groupdocs.com/merger/python-net/groupdocs.merger.domain/filetype/) — file type descriptor used to specify the output format.

## See also

- [Merge PDF files]({{< ref "merger/python-net/developer-guide/merge/pdf.md" >}})
- [More use-cases and complete Python via .NET sources]({{< ref "merger/python-net/showcases.md" >}})
