---
id: installation
url: merger/python-net/getting-started/installation
title: Installation
linkTitle: Installation
weight: 4
description: "Install GroupDocs.Merger for Python via .NET on Windows, Linux, or macOS — from PyPI or from a pre-downloaded wheel, with platform-specific notes for Linux native dependencies."
keywords: install, installation, pip, pypi, wheel, whl, Windows, Linux, macOS, manylinux, requirements.txt, GroupDocs.Merger, python, libgdiplus, libfontconfig
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
---

GroupDocs.Merger for Python via .NET is distributed as a pre-built wheel on [PyPI](https://pypi.org/project/groupdocs-merger-net/). The PyPI index hosts a separate wheel for each supported platform, and `pip` picks the correct one automatically.

Before installing, confirm your environment matches the supported platforms and Python versions listed in the [System Requirements]({{< ref "merger/python-net/getting-started/system-requirements.md" >}}) topic.

## Install from PyPI

Open a terminal and run the install command for your platform:

{{< tabs "install-pypi" >}}
{{< tab "Windows" >}}
```ps
py -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
# Install native dependencies first (required for rendering and font support)
sudo apt-get install -y libgdiplus libfontconfig1

python3 -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m pip install groupdocs-merger-net
```
{{< /tab >}}
{{< /tabs >}}

After running the command you should see output similar to:

```bash
Collecting groupdocs-merger-net
  Downloading groupdocs_merger_net-26.6-py3-none-win_amd64.whl.metadata (6.5 kB)
  Downloading groupdocs_merger_net-26.6-py3-none-win_amd64.whl (185.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 185.4/185.4 MB 3.1 MB/s eta 0:00:00
Installing collected packages: groupdocs-merger-net
Successfully installed groupdocs-merger-net-26.6
```

The wheel file name includes a platform suffix that matches your operating system — for example `manylinux1_x86_64` on Ubuntu/Debian or `win_amd64` on 64-bit Windows.

{{< alert style="info" >}}
**Linux note:** `libgdiplus` is required for page preview (image rendering) and `libfontconfig1` is required for correct font rendering. Install them with your system package manager before running any example that calls `generate_preview` or processes documents containing embedded fonts.
{{< /alert >}}

## Add the Package to `requirements.txt`

For reproducible environments, pin the package version in your `requirements.txt`:

```txt
groupdocs-merger-net
```

Then install all dependencies in one step:

```bash
pip install -r requirements.txt
```

## Install from a Pre-Downloaded Wheel

If your build environment cannot reach PyPI, download the appropriate wheel from the [GroupDocs Releases website](https://releases.groupdocs.com/merger/python-net/) and install it locally. The following wheels are published for each release:

| Platform | Wheel file name suffix |
|---|---|
| Windows 64-bit | `win_amd64.whl` |
| Linux x64 (glibc) | `manylinux1_x86_64.whl` |
| macOS Apple Silicon | `macosx_11_0_arm64.whl` |
| macOS Intel | `macosx_10_14_x86_64.whl` |

Place the downloaded wheel into your project folder, then install it:

{{< tabs "install-wheel" >}}
{{< tab "Windows (64-bit)" >}}
```ps
py -m pip install groupdocs_merger_net-26.6-py3-none-win_amd64.whl
```
{{< /tab >}}
{{< tab "Linux (glibc)" >}}
```bash
python3 -m pip install groupdocs_merger_net-26.6-py3-none-manylinux1_x86_64.whl
```
{{< /tab >}}
{{< tab "macOS (Apple Silicon)" >}}
```bash
python3 -m pip install groupdocs_merger_net-26.6-py3-none-macosx_11_0_arm64.whl
```
{{< /tab >}}
{{< tab "macOS (Intel)" >}}
```bash
python3 -m pip install groupdocs_merger_net-26.6-py3-none-macosx_10_14_x86_64.whl
```
{{< /tab >}}
{{< /tabs >}}

Expected output:

```bash
Processing groupdocs_merger_net-26.6-py3-none-*.whl
Installing collected packages: groupdocs-merger-net
Successfully installed groupdocs-merger-net-26.6
```

## Verify the Installation

Run the following one-liner to confirm the package is installed and importable:

{{< tabs "verify-install" >}}
{{< tab "Windows" >}}
```ps
py -c "from groupdocs.merger import Merger; print('GroupDocs.Merger installed OK')"
```
{{< /tab >}}
{{< tab "Linux / macOS" >}}
```bash
python3 -c "from groupdocs.merger import Merger; print('GroupDocs.Merger installed OK')"
```
{{< /tab >}}
{{< /tabs >}}

You should see:

```
GroupDocs.Merger installed OK
```

## Next Steps

- Follow the [Quick Start Guide]({{< ref "merger/python-net/getting-started/quick-start-guide" >}}) to merge your first document in under five minutes.
- Clone the [examples repository](https://github.com/groupdocs-merger/GroupDocs.Merger-for-Python-via-.NET) and read [How to Run Examples]({{< ref "merger/python-net/getting-started/how-to-run-examples.md" >}}) to try every documented scenario locally.
- If you work with AI agents or LLMs, see [Agents and LLM Integration]({{< ref "merger/python-net/agents-and-llm-integration" >}}) for MCP and `AGENTS.md` integration details.
