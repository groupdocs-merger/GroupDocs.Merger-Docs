---
id: mcp-tool-merge
url: merger/mcp/tools-reference/merge
title: merge
weight: 1
description: "The merge MCP tool combines 2–4 documents of the same format into a single file and saves the result to storage."
keywords: merge MCP tool, merge PDFs with AI agent, combine documents MCP, join files agent
productName: GroupDocs.Merger MCP Server
generated: true
serverVersion: 26.9.0
toc: True
---

`merge` combines **two to four documents** into one and saves the result. All inputs should be the same format family — all PDFs, or all DOCX. Example prompt: *"Merge these three PDFs into one document."*

**Tool description (as the AI agent sees it):**

> Merges 2–4 documents into a single file and saves the result to storage. Supports PDF, DOCX, XLSX, PPTX, and 30+ more document, image, and archive formats. All inputs should be the same format family for a clean merge (e.g. all PDFs, or all DOCX). Call this tool immediately whenever the user asks to merge, combine, or join documents together. Do NOT pre-check whether files exist — just pass the filenames the user provided. Returns a saved-path message ('Merged <a> + <b> into "<file>_merged.<ext>"') and the download URL or storage path. On failure, the response text starts with 'Merge failed for' followed by the underlying exception type, message, and inner-exception chain.

## Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `file1` | object | yes | First document — [FileInput shape]({{< ref "merger/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |
| `file2` | object | yes | Second document — [FileInput shape]({{< ref "merger/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |
| `file3` | object | no | Third document (optional) — [FileInput shape]({{< ref "merger/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |
| `file4` | object | no | Fourth document (optional) — [FileInput shape]({{< ref "merger/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |

## Example call

```json
{
  "name": "merge",
  "arguments": {
    "file1": {
      "filePath": "part-one.pdf"
    },
    "file2": {
      "filePath": "part-two.pdf"
    },
    "file3": {
      "filePath": "appendix.pdf"
    }
  }
}
```

## Result

A saved-path message naming the merged document in your output folder. The sources are untouched.

**Order is the argument order**: `file1`, then `file2`, and so on — so "put the appendix last" is a matter of which slot it occupies, and worth stating in the prompt.

For more than four documents, merge in rounds and chain each result into the next call. For mixed formats, convert first — see the [FAQ]({{< ref "merger/mcp/troubleshooting-faq.md" >}}).

On failure the text starts with `Merge failed for`, followed by the exception type and message.

## Example prompts

* *"Merge part-one.pdf and part-two.pdf into a single document."*
* *"Combine these three reports, with the appendix last."*
* *"Join the signed pages into one PDF for the archive."*

See it used end-to-end: [Merge documents with AI agents]({{< ref "merger/mcp/use-cases/merge-documents-with-ai-agents.md" >}}).
