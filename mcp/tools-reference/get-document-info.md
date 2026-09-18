---
id: mcp-tool-get-document-info
url: merger/mcp/tools-reference/get-document-info
title: get_document_info
weight: 3
description: "The get_document_info MCP tool returns file type, page count, size, and per-page dimensions — the precondition check before a merge or split."
keywords: get_document_info MCP, page count before merge, check document before split, MCP document info tool
productName: GroupDocs.Merger MCP Server
generated: true
serverVersion: 26.9.0
toc: True
---

`get_document_info` returns the file type, page count, size, and per-page dimensions without modifying anything. It is the natural precondition check: how many pages are there, and are these files even the same format? Example prompt: *"How many pages does each of these have?"*

**Tool description (as the AI agent sees it):**

> Returns the file type, page count, size, and per-page dimensions of a document as JSON, without modifying the file. Supports PDF, DOCX, XLSX, PPTX, and 30+ more document formats. Call this tool whenever the user asks to inspect a document, check its page count, or get its details — useful as a precondition check before Merge or Split (e.g. 'how many pages does this PDF have?'). Do NOT pre-check whether the file exists — just pass the filename the user provided. Returns a JSON object with fields `fileName`, `fileType`, `fileFormat`, `extension`, `pageCount`, `size`, and `pages` (array of `{ number, width, height, visible }`). On failure, the response text starts with 'Document-info lookup failed for' followed by the underlying exception type, message, and inner-exception chain.

## Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `file` | object | yes |  — [FileInput shape]({{< ref "merger/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |
| `password` | string | no | Password for protected documents |

## Example call

```json
{
  "name": "get_document_info",
  "arguments": {
    "file": {
      "filePath": "report.pdf"
    }
  }
}
```

## Result

A JSON object with `fileName`, `fileType`, `pageCount`, `sizeBytes`, and `pages` (width and height per page).

Two things it prevents: asking `split` for a page that does not exist, and merging a DOCX into a set of PDFs because nobody checked the extensions.

On failure the text starts with `Document-info lookup failed for`, followed by the exception type and message.

## Example prompts

* *"How many pages does each of these documents have?"*
* *"Are these all PDFs?"*
* *"What is the page size of this document?"*
