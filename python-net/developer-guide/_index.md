---
id: developer-guide
url: merger/python-net/developer-guide
title: Developer Guide
linkTitle: Developer Guide
weight: 3
description: "Step-by-step code examples for merging documents, splitting, extracting and removing pages, security operations, page preview, and loading documents with GroupDocs.Merger for Python via .NET. Every example is runnable in the companion GitHub repository."
keywords: developer guide, code examples, merge, split, extract pages, remove pages, rotate pages, password, preview, document info, python, GroupDocs.Merger
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
structuredData:
    showOrganization: True
---

Welcome to the Developer Guide for GroupDocs.Merger for Python via .NET. This section provides practical, runnable code examples designed to help you quickly integrate and use every GroupDocs.Merger API feature in your projects.

## Prerequisites

Before proceeding, please review:

- [System Requirements]({{< ref "merger/python-net/getting-started/system-requirements.md" >}}) — supported platforms, Python versions, and optional native dependencies.
- [Installation]({{< ref "merger/python-net/getting-started/installation.md" >}}) — install from PyPI or a pre-downloaded wheel.

We recommend [obtaining a Temporary License](https://purchase.groupdocs.com/temporary-license/) to test all product features without the evaluation page cap or watermark.

## How to Run a Code Example

This topic explains how to run any code example from the Developer Guide. We will demonstrate using the [Get Document Information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}}) example, but the steps are identical for every example.

### Step 1: Create a folder

```bash
mkdir get-document-information
cd get-document-information
```

### Step 2: Create and activate a virtual environment

Create:

{{< tabs "example1" >}}
{{< tab "Windows" >}}
```ps
py -m venv .venv
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 -m venv .venv
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m venv .venv
```
{{< /tab >}}
{{< /tabs >}}

Activate:

{{< tabs "example2" >}}
{{< tab "Windows" >}}
```ps
.venv\Scripts\activate
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
source .venv/bin/activate
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
source .venv/bin/activate
```
{{< /tab >}}
{{< /tabs >}}

### Step 3: Install `groupdocs-merger-net`

{{< tabs "example3" >}}
{{< tab "Windows" >}}
```ps
py -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< /tabs >}}

### Step 4: (Optional) Set the license

Set the `GROUPDOCS_LIC_PATH` environment variable with the absolute path to your license file, or copy the `.lic` file into the folder:

{{< tabs "example5" >}}
{{< tab "Windows (PowerShell)" >}}
```ps
$env:GROUPDOCS_LIC_PATH = "C:\path\to\GroupDocs.Merger.lic"
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
export GROUPDOCS_LIC_PATH="/path/to/GroupDocs.Merger.lic"
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
export GROUPDOCS_LIC_PATH="/path/to/GroupDocs.Merger.lic"
```
{{< /tab >}}
{{< /tabs >}}

### Step 5: Copy the code example

Create a file named `get_document_info.py` and paste the code from the [Get Document Information]({{< ref "merger/python-net/developer-guide/get-document-information.md" >}}) page.

### Step 6: Copy the input file

Download the sample `input.pdf` linked on the documentation page and place it in the same folder.

### Step 7: Run the example

{{< tabs "example6" >}}
{{< tab "Windows" >}}
```ps
py get_document_info.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 get_document_info.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 get_document_info.py
```
{{< /tab >}}
{{< /tabs >}}

## Sample Files

Alongside each code example you will find source files to download for reference. Each example uses `./input.<ext>` (and `./input2.<ext>` for merges) as its input path — place the downloaded sample file in the same directory as the script before running.

## Troubleshooting

If you encounter any issues while running the examples:

- Ensure all dependencies are installed correctly and that native libraries (`libgdiplus`, `libfontconfig1`) are present on Linux.
- Visit [Technical Support]({{< ref "merger/python-net/technical-support" >}}) for further assistance, or post on the [free support forum](https://forum.groupdocs.com/c/merger).
