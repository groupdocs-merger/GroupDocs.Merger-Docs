---
id: mcp
url: merger/mcp
title: GroupDocs.Merger MCP Server
weight: 6
description: "GroupDocs.Merger MCP server lets AI agents like Claude, Cursor, and Copilot merge documents and extract pages — PDF, Word, Excel, PowerPoint and 30+ formats — locally on your machine."
keywords: merge documents MCP server, merge PDFs with AI agent, split document MCP, combine files AI, Claude merge PDF locally
productName: GroupDocs.Merger MCP Server
hideChildren: True
toc: True
---

**GroupDocs.Merger MCP server** lets AI agents like Claude, Cursor, and Copilot **merge documents and extract pages** — PDF, Word, Excel, PowerPoint and 30+ more formats — **locally on your machine**. Nothing is uploaded to a web "merge PDF" service. 

Run it with one command. The Docker image is self-contained — the runtime and every native dependency the engine needs are inside it:

```bash
docker run --rm -i -v $(pwd)/documents:/data \
  ghcr.io/groupdocs-merger/merger-net-mcp:latest
```

With the .NET 10 SDK installed, the same server also runs without Docker:

```bash
dnx GroupDocs.Merger.Mcp --yes
```

Both are the **.NET** build of the server and run on Windows, Linux, and macOS. Other platforms will each get their own launcher — see [Install for your platform](#install-for-your-platform).

Or use the [guided installer]({{< ref "merger/mcp/getting-started/_index.md" >}}) to register the server in your AI client, verify the setup, and configure shared folders in one pass.

## What you can do

Four tools (full details in the [tools reference]({{< ref "merger/mcp/tools-reference/_index.md" >}})):

* **[`merge`]({{< ref "merger/mcp/tools-reference/merge.md" >}})** — combine two to four documents of the same format into one, in the order you give them.
* **[`split`]({{< ref "merger/mcp/tools-reference/split.md" >}})** — extract the pages you name, each saved as its own document.
* **[`get_document_info`]({{< ref "merger/mcp/tools-reference/get-document-info.md" >}})** — type, page count, size, per-page dimensions.
* **[`get_license_status`]({{< ref "merger/mcp/tools-reference/get-license-status.md" >}})** — active licensing mode and metered consumption.

Ask in plain language — *"combine these three reports with the appendix last"*, *"pull out the signature page"* — and the agent picks the tools.

## Install for your platform

Installation, prerequisites, and client configuration are platform-specific; the tools and licensing model below are the same everywhere.

| Platform | Status | Install and setup |
|---|---|---|
| .NET | **Available** | [MCP server for .NET]({{< ref "merger/net/mcp/_index.md" >}}) |
| Java | Planned | [Tell us you need it](https://forum.groupdocs.com/c/merger/32) |
| Python | Planned | [Tell us you need it](https://forum.groupdocs.com/c/merger/32) |
| Node.js | Planned | [Tell us you need it](https://forum.groupdocs.com/c/merger/32) |

## Two things to know before you start

**Four documents per merge.** One `merge` call takes `file1`–`file4`. For more, merge in rounds and chain each result into the next call — an agent will do the bookkeeping if you ask.

**Same format family.** All PDFs, or all DOCX. Mixing a Word file into a set of PDFs has no defined result; convert first with the [GroupDocs.Conversion MCP server]({{< ref "conversion/mcp/_index.md" >}}), then merge.

{{< alert style="warning" >}}
**Evaluation mode trims the result to three pages** and stamps a trial badge on each one — silently. A merge of four long PDFs comes back as three pages and looks like it worked. Check [`get_license_status`]({{< ref "merger/mcp/tools-reference/get-license-status.md" >}}) before a real run; see [Licensing]({{< ref "merger/mcp/getting-started/licensing.md" >}}).
{{< /alert >}}

## Supported AI clients

| Client | How it connects |
|---|---|
| Claude Desktop | `claude_desktop_config.json` |
| Claude Code | `claude mcp add` CLI |
| VS Code / GitHub Copilot | user-level or workspace `mcp.json` |
| Visual Studio 2022 (17.14+) | `.mcp.json` in the solution root |
| Cursor | `~/.cursor/mcp.json` |
| Windsurf | `~/.codeium/windsurf/mcp_config.json` |
| Cline | Cline MCP settings |
| Codex CLI | `codex mcp add` CLI |
| JetBrains Rider | manual registration (Settings → AI Assistant → MCP) |

Exact config blocks for every client: [Register in AI clients]({{< ref "merger/net/mcp/install-in-ai-clients.md" >}}).

## Delivery channels

| | Docker (recommended) | NuGet (`dnx`) |
|---|---|---|
| Prerequisites | Docker only | .NET 10 SDK (+ `libgdiplus` on Linux/macOS) |
| Native dependencies | bundled in the image | installed by you (or the setup script) |
| Package | `ghcr.io/groupdocs-merger/merger-net-mcp` | `GroupDocs.Merger.Mcp` on NuGet |
| Architectures | linux/amd64 + linux/arm64 (Apple Silicon native) | any OS with .NET 10 |

## How it works

The server uses MCP's **local stdio transport**: your AI client starts the server as a child process and talks to it over standard input/output. No inbound ports, no external endpoints, no telemetry — the data path is *agent → local server → local filesystem*. Details: [On-premise architecture]({{< ref "merger/mcp/use-cases/on-premise-document-merging.md" >}}).

## When you need more than a free online merge tool

The web is full of "merge PDF" pages, and every one of them asks you to upload the document. Choose this server when you need: the merge to happen **on your machine**; the **same model across 30+ formats**, not just PDF; format-preserving merges rather than flattened output; merging and splitting **inside an agent workflow** rather than by hand; and the fidelity of the commercial GroupDocs engine trusted by enterprise teams for over a decade.

## Resources

* [Quick start]({{< ref "merger/mcp/getting-started/_index.md" >}}) · [Use cases]({{< ref "merger/mcp/use-cases/_index.md" >}}) · [Troubleshooting & FAQ]({{< ref "merger/mcp/troubleshooting-faq.md" >}})
* GitHub: [server source](https://github.com/groupdocs-merger/GroupDocs.Merger.Mcp) · [installer](https://github.com/groupdocs/GroupDocs.Mcp.Installer) · [integration tests](https://github.com/groupdocs-merger/GroupDocs.Merger.Mcp.Tests)
* [NuGet package](https://www.nuget.org/packages/GroupDocs.Merger.Mcp) · [Docker image](https://github.com/orgs/groupdocs-merger/packages/container/package/merger-net-mcp) · [MCP Registry](https://registry.modelcontextprotocol.io/v0/servers?search=io.github.groupdocs-merger/groupdocs-merger-mcp)
* Questions: [Merger forum](https://forum.groupdocs.com/c/merger/32)
