---
id: groupdocs-merger-for-java-23-2-release-notes
url: merger/java/groupdocs-merger-for-java-23-2-release-notes
title: GroupDocs.Merger for Java 23.2 Release Notes
weight: 120
description: ""
keywords: 
productName: GroupDocs.Merger for Java
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Merger for Java 23.2{{< /alert >}}

## Major Features

There are few fixed bugs and new features in this regular monthly release. The most notable are:

*   Implemented image cross-merging from-to JPG, JPEG, PNG, BMP;
*   Implemented image to PDF joining: BMP, PNG, JPG, JPEG, GIF, TIF and TIFF;
*   Implemented TIF and TIFF file splitting;
*   Fixed "Image file cannot be written to disk" bug for HTML and MHTML.

## Full List of Issues Covering all Changes in this Release

| Key | Summary | Category |
| --- | --- | --- |
| MERGERNET-1276 | Image cross-merging from-to JPG, JPEG, PNG, BMP | Feature |
| MERGERNET-1278 | Image to PDF joining: BMP, PNG, JPG, JPEG, GIF, TIF and TIFF | Feature |
| MERGERNET-1287 | TIF and TIFF file splitting | Feature |
| MERGERNET-1337 | Image file cannot be written to disk for HTML and MHTML | Bug |

## Public API and Backward Incompatible Changes

{{< alert style="info" >}}This section lists public API changes that were introduced in GroupDocs.Merger for Java 23.2. It includes not only new and obsoleted public methods, but also a description of any changes in the behavior behind the scenes in GroupDocs.Merger which may affect existing code. Any behavior introduced that could be seen as a regression and modifies existing behavior is especially important and is documented here.{{< /alert >}}


### The existing Join method of the Merger class was expanded

The existing **[join](https://reference.groupdocs.com/merger/java/com.groupdocs.merger/merger/#join-java.io.InputStream-)** method of the GroupDocs.Merger for Java product was expanded, please refer to the following documentation articles for more details:

*   [How to merge images to JPEG file]({{< ref "merger/java/getting-started/use-cases/how-to-merge-images-to-jpeg-using-java.md" >}});
*   [How to merge images to PDF file]({{< ref "merger/java/getting-started/use-cases/how-to-merge-images-to-pdf-using-java.md" >}}).
