---
id: mcp-tool-split
url: merger/mcp/tools-reference/split
title: split
weight: 2
description: "The split MCP tool extracts the pages you name from a document, saving each extracted page as its own file."
keywords: split MCP tool, extract pages from PDF AI, split document agent, separate pages MCP
productName: GroupDocs.Merger MCP Server
generated: true
serverVersion: 26.9.0
toc: True
---

`split` extracts the pages you name — `pages: "3,6,8"` — and saves **each one as its own document**. Example prompt: *"Pull out pages 3, 6, and 8 as separate files."*

**Tool description (as the AI agent sees it):**

> Splits a document by extracting specific pages, saving each extracted page as an individual document to storage. Supports PDF, DOCX, XLSX, PPTX, and 30+ more multi-page document formats. Call this tool immediately whenever the user asks to split, extract pages, or separate a document into parts. Do NOT pre-check whether files exist — just pass the filename the user provided. Pass page numbers as a comma-separated 1-based list, e.g. pages='3,6,8'. Returns a message ('Split "<file>" into N file(s):') followed by the saved path of each extracted document. On failure, the response text starts with 'Split failed for' followed by the underlying exception type, message, and inner-exception chain.

## Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `file` | object | yes |  — [FileInput shape]({{< ref "merger/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |
| `pages` | string | yes | Page numbers to extract as separate documents (1-based), e.g. '3,6,8' |
| `password` | string | no | Password for protected documents |

## Example call

```json
{
  "name": "split",
  "arguments": {
    "file": {
      "filePath": "report.pdf"
    },
    "pages": "3,6,8"
  }
}
```

## Result

A message naming the extracted documents, one per requested page.

This is page **extraction**, not range splitting: three page numbers produce three single-page files, not one file containing those three pages. To get a single document with pages 3, 6 and 8, extract them and then [`merge`]({{< ref "merger/mcp/tools-reference/merge.md" >}}) the results — two prompts, and an agent will chain them if you ask.

Call [`get_document_info`]({{< ref "merger/mcp/tools-reference/get-document-info.md" >}}) first if you are unsure how many pages exist; asking for page 12 of a ten-page document fails rather than silently returning less.

On failure the text starts with `Split failed for`, followed by the exception type and message.

## Example prompts

* *"Pull out pages 3, 6, and 8 as separate files."*
* *"Extract the signature page from this contract."*
* *"Split out the first page of each of these documents."*

See it used end-to-end: [Split and reassemble documents]({{< ref "merger/mcp/use-cases/split-and-reassemble-documents.md" >}}).
