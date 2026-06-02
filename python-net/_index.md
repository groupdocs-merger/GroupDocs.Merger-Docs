---
id: home
url: merger/python-net
title: GroupDocs.Merger for Python via .NET
weight: 1
description: "Native Python library that merges, splits, and reorganises documents — PDF, DOCX, XLSX, PPTX, images, and more — entirely on-premise. No Microsoft Office required."
keywords: GroupDocs.Merger, Python via .NET, merge documents, split document, remove pages, rotate pages, password protection, PDF, DOCX, XLSX, PPTX, on-premise, Windows, Linux, macOS
productName: GroupDocs.Merger for Python via .NET
hideChildren: True
toc: True
layout: single
structuredData:
    showOrganization: True
---

<img src="/logo/128x128/groupdocs-merger-python.png" alt="GroupDocs.Merger for Python via .NET" align="left" style="width:110px; margin: 0 30px 30px 0"/>

<img src="https://img.shields.io/pypi/v/groupdocs-merger-net?label=GroupDocs.Merger%20PyPI" alt="PyPI package">
<img src="https://img.shields.io/pypi/dm/groupdocs-merger-net?label=pypi%20downloads" alt="PyPI downloads">

{{< button style="primary" link="https://releases.groupdocs.com/merger/python-net/release-notes/" >}} <svg class="gdoc-icon gdoc-product-doc__btn-icon"><use xlink:href="/img/groupdocs-stack.svg#document"></use></svg> Release notes {{< /button >}}
{{< button style="primary" link="https://pypi.org/project/groupdocs-merger-net/" >}} {{< icon "gdoc_download" >}} Download from PyPI {{< /button >}}
{{< button style="primary" link="https://products.groupdocs.app/merger/total" >}} <svg class="gdoc-icon gdoc-product-doc__btn-icon"><use xlink:href="/img/groupdocs-stack.svg#app"></use></svg> Online app {{< /button >}}

[GroupDocs.Merger for Python via .NET](https://products.groupdocs.com/merger/python-net/) is a document manipulation API that lets you merge multiple documents into one, split a single document into many, and reorganise pages — all without Microsoft Office, Adobe Acrobat, or any other third-party application.

<div style="clear:left"></div>

## Quick example

```python
from groupdocs.merger import Merger

# Merge two documents into one
with Merger("document1.docx") as merger:
    merger.join("document2.docx")
    merger.save("merged.docx")
```

## Features

- **Merge and join** — combine multiple documents or selected pages into a single file.
- **Split** — divide a document into individual pages or multi-page segments.
- **Page operations** — extract, remove, swap, move, rotate, or change the orientation of pages.
- **Security** — add, update, remove, or check document passwords.
- **Document inspection** — read file type, page count, dimensions, and other metadata without modifying the file.
- **Page preview** — generate PNG, JPEG, or BMP preview images of document pages.

## Supported File Formats

GroupDocs.Merger supports merging and manipulating documents across a wide range of formats. For the complete list see [Supported Document Formats]({{< ref "merger/python-net/getting-started/supported-document-formats.md" >}}).

- **Word Processing** (DOCX, DOC, DOTX, RTF, ODT)
- **Spreadsheets** (XLSX, XLS, ODS, CSV)
- **Presentations** (PPTX, PPT, ODP)
- **PDF** (PDF, PDF/A)
- **Visio** (VSDX, VSD, VSTX)
- **Images** (PNG, JPEG, BMP, TIFF, GIF)
- **eBooks** (EPUB, MOBI)

## Getting Started

- [System Requirements]({{< ref "merger/python-net/getting-started/system-requirements.md" >}}) — supported platforms and Python versions.
- [Installation]({{< ref "merger/python-net/getting-started/installation.md" >}}) — install from PyPI or a pre-downloaded wheel.
- [Quick Start Guide]({{< ref "merger/python-net/getting-started/quick-start-guide" >}}) — merge, extract, and split a document in under five minutes.

## Developer Guide

The [Developer Guide]({{< ref "merger/python-net/developer-guide" >}}) provides runnable code examples for every API feature — merging by format, splitting, page-level operations, security, previewing, and loading documents.

## Technical Support

If you experience any issues or have suggestions, visit the [Technical Support]({{< ref "merger/python-net/technical-support" >}}) page. The [free support forum](https://forum.groupdocs.com/c/merger) is also available for questions answered directly by the development team.
