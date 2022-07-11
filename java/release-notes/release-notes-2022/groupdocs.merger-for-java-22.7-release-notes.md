---
id: groupdocs-merger-for-java-22-7-release-notes
url: merger/java/groupdocs-merger-for-java-22-7-release-notes
title: GroupDocs.Merger for Java 22.7 Release Notes
weight: 100
description: ""
keywords: 
productName: GroupDocs.Merger for Java
hideChildren: False
---
{{< alert style="info" >}}## NOTE: Starting from this release of the GroupDocs.Merger for Java will support version Java 8 and above.{{< /alert >}}
{{< alert style="info" >}}This page contains release notes for GroupDocs.Merger for Java 22.7{{< /alert >}}

## Major Features

There are few bugs in this regular monthly release. The most notable are:

*   Implemented image joining: JPG, BMP, PNG;
*   Implemented merging of Word documents without starting from a new page.
*   Save method with FilePath parameter doesn't work as expected.

## Full List of Issues Covering all Changes in this Release

| Key | Summary | Category |
| --- | --- | --- |
| MERGERNET-1201 | Implement image joining: JPG, BMP, PNG | Feature |
| MERGERNET-1208 | Implement merging of Word documents without starting from a new page | Feature |
| MERGERNET-1231 | Save method with FilePath parameter doesn't work as expected | Bug |

## Public API and Backward Incompatible Changes

{{< alert style="info" >}}This section lists public API changes that were introduced in GroupDocs.Merger for Java 22.7. It includes not only new and obsoleted public methods, but also a description of any changes in the behavior behind the scenes in GroupDocs.Merger which may affect existing code. Any behavior introduced that could be seen as a regression and modifies existing behavior is especially important and is documented here.{{< /alert >}}

### The existing Join method of the Merger class was expanded

The existing **[Join](https://apireference.groupdocs.com/merger/java/com.groupdocs.merger/Merger#join(java.io.InputStream))** method of the GroupDocs.Merger for Java product was expanded, please refer to the following documentation articles for more details:

*   [How to merge image files]({{< ref "merger/java/developer-guide/merge/images.md" >}});
*   [How to merge Word documents without starting from a new page]({{< ref "merger/java/developer-guide/merge/word.md#how-to-merge-word-documents-without-starting-from-a-new-page" >}}).
