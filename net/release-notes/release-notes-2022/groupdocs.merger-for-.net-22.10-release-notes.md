---
id: groupdocs-merger-for-net-22-10-release-notes
url: merger/net/groupdocs-merger-for-net-22-10-release-notes
title: GroupDocs.Merger for .NET 22.10 Release Notes
weight: 80
description: ""
keywords: 
productName: GroupDocs.Merger for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Merger for .NET 22.10{{< /alert >}}

## Major Features

There are few fixed bugs and a new feature in this regular monthly release. The most notable are:

*   Implemented image joining: GIF, TIF, TIFF;
*   Fixed broken slide formatting when joining pptx files;
*   Fixed the given key was not present in the dictionary.

## Full List of Issues Covering all Changes in this Release

| Key | Summary | Category |
| --- | --- | --- |
| MERGERNET-1294 | Implement image joining: GIF, TIF, TIFF | Feature |
| MERGERNET-1290 | Broken slide formatting when joining pptx files | Bug |
| MERGERNET-1293 | The given key was not present in the dictionary | Bug |

## Public API and Backward Incompatible Changes

{{< alert style="info" >}}This section lists public API changes that were introduced in GroupDocs.Merger for .NET 22.10. It includes not only new and obsoleted public methods, but also a description of any changes in the behavior behind the scenes in GroupDocs.Merger which may affect existing code. Any behavior introduced that could be seen as a regression and modifies existing behavior is especially important and is documented here.{{< /alert >}}


### The existing Join method of the Merger class was expanded

The existing **[Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join)** method of the GroupDocs.Merger for .NET product was expanded, please refer to the following documentation articles for more details:

*   [How to merge TIF image files]({{< ref "merger/net/getting-started/use-cases/how-to-merge-tif-images-using-csharp.md" >}});
*   [How to merge GIF image files]({{< ref "merger/net/getting-started/use-cases/how-to-merge-gif-images-using-csharp.md" >}});
*   [How to merge TIFF image files]({{< ref "merger/net/getting-started/use-cases/how-to-merge-tiff-images-using-csharp.md" >}}).
