---
id: groupdocs-merger-for-java-21-7-release-notes
url: merger/java/groupdocs-merger-for-java-21-7-release-notes
title: GroupDocs.Merger for Java 21.7 Release Notes
weight: 90
description: ""
keywords: 
productName: GroupDocs.Merger for Java
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Merger for Java 21.7{{< /alert >}}

## Major Features

There are a few fixed bugs and improvements in this regular monthly release. The most notable are:

*   The surrogate pair (0xD83D, 0xD83D) is invalid. A high surrogate character (0xD800 - 0xDBFF) must always be paired with a low surrogate character (0xDC00 - 0xDFFF);
*   The method or operation is not implemented;
*   Object reference not set to an instance of an object;
*   Failed to detect file type;
*   PowerPoint Slides size changed after merging;
*   Expanded IJoinOptions with FileType property and involved it to Join method;
*   GeneratePreview fails under linux.


## Full List of Issues Covering all Changes in this Release

| Key | Summary | Category |
| --- | --- | --- |
| MERGERNET-1010 | Object reference not set to an instance of an object | Bug |
| MERGERNET-1030 | The surrogate pair (0xD83D, 0xD83D) is invalid. A high surrogate character (0xD800 - 0xDBFF) must always be paired with a low surrogate character (0xDC00 - 0xDFFF) | Bug |
| MERGERNET-1054 | The method or operation is not implemented | Bug |
| MERGERNET-1078 | Failed to detect file type | Bug |
| MERGERNET-1079 | PowerPoint Slides size changed after merging | Bug |
| MERGERNET-1104 | Expand IJoinOptions with FileType property and involve it to Join method | Improvement |
| MERGERNET-1105 | GeneratePreview fails under linux | Bug |

## Public API and Backward Incompatible Changes

{{< alert style="info" >}}This section lists public API changes that were introduced in GroupDocs.Merger for Java 21.6. It includes not only new and obsoleted public methods, but also a description of any changes in the behavior behind the scenes in GroupDocs.Merger which may affect existing code. Any behavior introduced that could be seen as a regression and modifies existing behavior is especially important and is documented here.{{< /alert >}}

### None.
