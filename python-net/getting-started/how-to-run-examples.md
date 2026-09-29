---
id: how-to-run-examples
url: merger/python-net/getting-started/how-to-run-examples
title: How to Run Examples
linkTitle: How to Run Examples
weight: 7
description: "Clone the GitHub examples repository, install dependencies into a virtual environment, optionally apply a license, and run every documented GroupDocs.Merger example end to end — locally, inside Docker, or on GitHub Actions."
keywords: run examples, examples repository, github, docker, dockerfile, CI, GitHub Actions, venv, virtual environment, run_all_examples, GROUPDOCS_LIC_PATH, GroupDocs.Merger, python
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
aliases:
    - /merger/python-net/how-to-run-examples/
---

Every code example shown on this documentation site lives in a standalone, runnable form in the [GroupDocs.Merger-for-Python-via-.NET](https://github.com/groupdocs-merger/GroupDocs.Merger-for-Python-via-.NET) repository on GitHub. Each example ships with its input sample files, so you can clone the repo and run anything with a single command.

## Prerequisites

Before running the examples, make sure you have:

1. **A supported platform and Python version** — see [System Requirements]({{< ref "merger/python-net/getting-started/system-requirements.md" >}}). Windows, Linux, and macOS (Intel and Apple Silicon) are all supported.
2. **Git** — or download the repository as a ZIP from GitHub.
3. **A license file** (optional but recommended) — without one, the library runs in evaluation mode with a watermark on output and a 3-page cap on multi-page operations. See [Licensing]({{< ref "merger/python-net/getting-started/licensing-and-subscription.md" >}}) for how to obtain a free temporary license.

## Get the Code

Clone the repository and navigate into it:

```bash
git clone https://github.com/groupdocs-merger/GroupDocs.Merger-for-Python-via-.NET.git
cd GroupDocs.Merger-for-Python-via-.NET
```

## Project Structure

The repository mirrors this documentation tree. Every documentation page maps to a folder under `Examples/`, and every tabbed code block on a page maps to a `.py` file inside that folder. Input sample files live next to the script that reads them.

```
GroupDocs.Merger-for-Python-via-.NET
├── README.md
├── LICENSE
├── AGENTS.md                          ← extracted from the pip package for AI tools
├── Dockerfile                         ← runs the whole suite on Linux
├── .github/workflows/run-examples.yml ← CI: runs all examples on every push
└── Examples
    ├── requirements.txt
    ├── run_all_examples.py
    ├── getting-started
    │   └── quick-start-guide
    │       ├── merge_two_documents.py
    │       ├── extract_pages_from_pdf.py
    │       ├── split_document_pages.py
    │       ├── input.docx
    │       └── input.pdf
    ├── developer-guide
    │   ├── merge
    │   │   ├── merge_pdf_documents.py
    │   │   ├── merge_word_documents.py
    │   │   ├── merge_excel_documents.py
    │   │   ├── merge_powerpoint_documents.py
    │   │   └── (sample inputs: input.pdf, input.docx, input.xlsx, ...)
    │   ├── single-document-operations
    │   │   ├── split_document.py
    │   │   ├── extract_pages.py
    │   │   ├── remove_pages.py
    │   │   ├── swap_pages.py
    │   │   ├── move_page.py
    │   │   ├── rotate_pages.py
    │   │   └── change_page_orientation.py
    │   ├── security-operations
    │   │   ├── add_document_password.py
    │   │   ├── update_document_password.py
    │   │   ├── remove_document_password.py
    │   │   └── check_document_password.py
    │   ├── get_document_information.py
    │   ├── get_supported_file_types.py
    │   ├── page_preview.py
    │   └── loading-documents
    │       ├── load_from_local_disk.py
    │       ├── load_from_stream.py
    │       └── load_password_protected.py
    └── licensing
        ├── set_license_from_file.py
        └── set_metered_license.py
```

## Setup

1. **Create and activate a virtual environment**:

   Create:

   {{< tabs "venv-create" >}}
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

   {{< tabs "venv-activate" >}}
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

2. **Install dependencies** from `Examples/requirements.txt`:

   {{< tabs "install-deps" >}}
   {{< tab "Windows" >}}
   ```ps
   py -m pip install -r Examples/requirements.txt
   ```
   {{< /tab >}}
   {{< tab "Linux" >}}
   ```bash
   python3 -m pip install -r Examples/requirements.txt
   ```
   {{< /tab >}}
   {{< tab "macOS" >}}
   ```bash
   python3 -m pip install -r Examples/requirements.txt
   ```
   {{< /tab >}}
   {{< /tabs >}}

3. **Configure a license** (optional). The suite honours the `GROUPDOCS_LIC_PATH` environment variable. Set it in your shell before running `run_all_examples.py`:

   {{< tabs "license-env" >}}
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

   {{< alert style="info" >}}
   Learn more about licensing, evaluation limits, and how to obtain a free 30-day temporary license in the [Licensing]({{< ref "merger/python-net/getting-started/licensing-and-subscription.md" >}}) documentation topic.
   {{< /alert >}}

## Run the Examples

### Run the Full Suite

From the repository root, invoke `run_all_examples.py`. It imports every example in order, prints a per-file status line, and exits with a pass/fail summary.

{{< tabs "run-all" >}}
{{< tab "Windows" >}}
```ps
py Examples\run_all_examples.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 Examples/run_all_examples.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 Examples/run_all_examples.py
```
{{< /tab >}}
{{< /tabs >}}

### Run a Single Example

Change into the folder that contains the script and run it directly. Input sample files live next to each script, so relative paths resolve correctly.

```bash
cd Examples/getting-started/quick-start-guide
python3 merge_two_documents.py
```

Every example writes its output artefacts into the same folder as the script.

### Run with Docker

The repository includes a `Dockerfile` that installs the ICU runtime, `libgdiplus`, `libfontconfig1`, and every Python dependency, then runs the full suite. Use it when you want a clean, reproducible Linux environment:

```bash
docker build -t groupdocs-merger-examples .
docker run --rm \
    -e GROUPDOCS_LIC_PATH=/license/GroupDocs.Merger.lic \
    -v /path/to/your/license:/license:ro \
    groupdocs-merger-examples
```

### Continuous Integration

Every push to `main` triggers `.github/workflows/run-examples.yml`, which runs the entire example suite on `ubuntu-latest` with Python 3.13. Fork the repository and open a pull request — the workflow runs for free on GitHub-hosted runners.

## Troubleshooting

- **`DllNotFoundException: libgdiplus`** on Linux — install the native dependency: `sudo apt-get install libgdiplus libfontconfig1`. See [System Requirements]({{< ref "merger/python-net/getting-started/system-requirements.md" >}}).
- **Garbled text or missing glyphs** — install Microsoft TrueType fonts (`ttf-mscorefonts-installer` on Debian/Ubuntu) and run `fc-cache -f` so fontconfig picks them up.
- **Evaluation watermark / page cap (3 pages)** — set `GROUPDOCS_LIC_PATH` to a valid license file and re-run. In evaluation mode, multi-page documents are capped at 3 pages and outputs carry a watermark. Operations on documents with 3 pages or fewer are unaffected. See [Licensing]({{< ref "merger/python-net/getting-started/licensing-and-subscription.md" >}}).
- **Anything else** — post on the [free support forum](https://forum.groupdocs.com/c/merger) or visit the [Technical Support]({{< ref "merger/python-net/technical-support" >}}) page.
