---
id: mcp-troubleshooting-faq
url: merger/mcp/troubleshooting-faq
title: Troubleshooting & FAQ
weight: 5
description: "Solutions to the most common GroupDocs.Merger MCP server issues — server not appearing in the client, startup failures, missing native dependencies, and first-launch timeouts."
keywords: MCP server not showing up in Claude Desktop, Claude can't see MCP tools, MCP server failed to start, dnx command not found, libgdiplus not found error, merge PDFs AI agent, split document MCP, combine documents Claude, extract pages agent
productName: GroupDocs.Merger MCP Server
toc: True
---

Solutions to the most common GroupDocs.Merger MCP server issues — server not appearing in the client, startup failures, missing native dependencies, and first-launch timeouts.

{{< alert style="info" >}}
**Platform-specific troubleshooting:** runtime problems depend on which build you run. For the `dnx` runner, native graphics libraries, and the Docker channel, see [Troubleshooting (.NET)]({{< ref "merger/net/mcp/troubleshooting.md" >}}). The issues on this page apply to every platform.
{{< /alert >}}

## Why is my MCP server not showing up in Claude Desktop?

1. **Restart the client** — every client reads its MCP config only at startup.
2. Check the config file location for your OS ([per-client reference]({{< ref "merger/net/mcp/install-in-ai-clients.md" >}})) and that the entry sits under the right root key (`mcpServers` for Claude Desktop/Cursor/Windsurf, `servers` for VS Code/VS 2022).
3. Validate the JSON — a trailing comma silently breaks the whole file. If you used the [installer](https://github.com/groupdocs/GroupDocs.Mcp.Installer), a timestamped `.bak` of your previous config sits next to the file for comparison.

## The first tool call is slow or fails once, then works

A **cold cache**: on the very first use the server's package or image is still downloading while the client is already waiting on the connection. Warming it once fixes it for good — the exact command depends on your build: [.NET]({{< ref "merger/net/mcp/troubleshooting.md" >}}#the-first-tool-call-is-slow-or-fails-once-and-then-works).

## The server fails to start, or a runtime dependency is missing

These are properties of the build you run rather than of MCP, so the fixes live with the platform:

| Symptom | Where the fix is |
|---|---|
| `dnx: command not found` | [.NET troubleshooting]({{< ref "merger/net/mcp/troubleshooting.md" >}}#dnx-command-not-found) — `dnx` ships inside the .NET 10 SDK |
| `DllNotFoundException: libgdiplus` on Linux/macOS | [.NET troubleshooting]({{< ref "merger/net/mcp/troubleshooting.md" >}}#dllnotfoundexception-libgdiplus) — install the native graphics libraries, or use the Docker image |
| "docker daemon not reachable" | [.NET troubleshooting]({{< ref "merger/net/mcp/troubleshooting.md" >}}#docker-daemon-not-reachable) — start Docker Desktop or `dockerd` |

## The agent says a file does not exist

Pass the **file name**, not a full path from your machine: the server resolves names inside its configured storage folder. When a name is not found the tool responds with the list of files it can see, so the agent can correct itself — check that list against [`GROUPDOCS_MCP_STORAGE_PATH`]({{< ref "merger/net/mcp/configuration.md" >}}).

## Why only four documents per merge?

The MCP tool exposes `file1`–`file4`, so one call combines at most four. For more, **merge in rounds**: combine four, then merge that result with the next three, and so on. An agent handles the bookkeeping if you ask it to — *"merge them four at a time, chaining each result into the next call"*. The underlying library has no such limit; if you need a larger fan-in through MCP, say so in the [forum](https://forum.groupdocs.com/c/merger/32).

## Can I merge a PDF with a Word document?

Not in one call. Inputs should be the **same format family** — all PDFs, or all DOCX — otherwise the merge is undefined. Convert first with the [GroupDocs.Conversion MCP server](/conversion/mcp/), then merge the matching set.

## How do I split a document in half?

`split` extracts **specific pages**, each as its own file — `pages: "3,6,8"` gives you three single-page documents. It is page extraction, not "cut here". To produce a document containing pages 1-10, extract those pages and merge the results, or use the library directly for range-based splitting.

## Does merging preserve formatting?

The engine merges documents in their own format, preserving layout, styles, and structure — it is not a print-to-PDF concatenation. Fonts and styles that differ between sources remain different in the result, which is usually what you want and occasionally surprising.

## Why is my merged file only three pages?

Evaluation mode trims the result to the first three pages. Check with [`get_license_status`]({{< ref "merger/mcp/tools-reference/get-license-status.md" >}}) before concluding the merge failed.

## Verifying an installation end-to-end

Ask your agent *"list your GroupDocs merge tools and the license status"* — it should name `merge`, `split`, `get_document_info`, `get_license_status`. For a scripted check that performs the real MCP handshake and a live call through the engine, see [verifying a .NET installation]({{< ref "merger/net/mcp/troubleshooting.md" >}}#verifying-an-installation-end-to-end).

## Still stuck?

Post your config (redact license paths) and the client name in the [Merger forum](https://forum.groupdocs.com/c/merger/32) — we answer MCP questions daily. Bugs: [GitHub issues](https://github.com/groupdocs-merger/GroupDocs.Merger.Mcp/issues).
