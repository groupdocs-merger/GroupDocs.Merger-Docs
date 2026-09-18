---
id: mcp-supported-formats
url: merger/mcp/supported-formats
title: Supported formats
weight: 4
description: "The MCP server exposes the full GroupDocs.Merger engine: PDF, Word, Excel, PowerPoint, images, archives and 30+ more formats can be merged and split through your AI agent."
keywords: MCP server supported formats, merge pdf MCP, merge docx MCP, split presentation MCP, merge archives
productName: GroupDocs.Merger MCP Server
toc: True
---

The MCP server exposes the **full GroupDocs.Merger engine**: every format the .NET library can merge and split — 30+ document, spreadsheet, presentation, image, and archive formats — is available to your AI agent. The canonical matrix lives in the library documentation: [supported document formats]({{< ref "merger/net/getting-started/supported-document-formats.md" >}}).

What agents are asked for most:

* **PDF** — the common case: combine parts, extract a page, assemble a pack.
* **DOCX / DOC** — merge sections while the document is still editable, rather than converting to PDF first.
* **XLSX** — combine workbooks; `split` extracts by **worksheet position** in spreadsheet formats.
* **PPTX** — join decks, or pull out the slides you need.

**The rule that governs every merge: same format family.** All PDFs, or all DOCX, or all XLSX. This is not an arbitrary restriction — combining a spreadsheet with a presentation has no meaningful result. When sources differ, convert them to a common format first with the [GroupDocs.Conversion MCP server]({{< ref "conversion/mcp/_index.md" >}}), then merge the matching set.

Unsure what you are holding? Ask — *"are these all the same format, and how many pages each?"* — and the agent answers via [`get_document_info`]({{< ref "merger/mcp/tools-reference/get-document-info.md" >}}).
