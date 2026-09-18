---
id: mcp-uc-merge-documents-with-ai-agents
url: merger/mcp/use-cases/merge-documents-with-ai-agents
title: How to merge documents with AI agents using MCP
linkTitle: Merge with AI agents
weight: 1
description: "Merge documents with an AI agent over MCP: combine two to four files of the same format locally, control the order, and chain rounds for larger sets."
keywords: merge documents with AI agent, MCP merge PDF, Claude combine documents, join files locally
productName: GroupDocs.Merger MCP Server
toc: True
structuredData:
    showOrganization: True
    howTo:
        name: "How to merge documents with AI agents using MCP"
        description: "Merge documents with an AI agent over MCP: combine two to four files of the same format locally, control the order, and chain rounds for larger sets."
        steps:
        - name: "Install the server"
          text: "Run the GroupDocs.Merger MCP server with Docker or dnx and register it in your AI client."
        - name: "Put the documents in the storage folder"
          text: "Point GROUPDOCS_MCP_STORAGE_PATH at the folder that holds the files the agent should use."
        - name: "Ask the agent"
          text: "There are nine PDFs. Merge them four at a time, chaining each result into the next call, and tell me the final file name."
---

Merging through an agent replaces the most-uploaded task on the internet with a local tool call. The documents stay on your machine; the combined file appears in your output folder.

{{< alert style="info" >}}
The commands and config snippets on this page are for the **.NET** build of the server — the only platform available today. Installation and client setup: [MCP server for .NET]({{< ref "merger/net/mcp/_index.md" >}}). Other platforms will expose the same tools with their own launch command; everything else on this page applies unchanged.
{{< /alert >}}

## The pattern

1. Put the documents in the storage folder the server can see.
2. Ask: *"Merge part-one.pdf, part-two.pdf and appendix.pdf into one document, appendix last."*
3. The agent calls [`merge`]({{< ref "merger/mcp/tools-reference/merge.md" >}}) with the files in slots `file1`–`file4`.
4. The combined document appears in your output folder; the sources are untouched.

## Order is the slot order

`file1` comes first, `file4` last. "Appendix last" is a positional instruction, and if the order matters, say it — an agent given three names in an arbitrary sentence may not infer the sequence you had in mind. Asking it to confirm the order before the call costs nothing.

## More than four documents

One call takes four. For more, merge in **rounds**:

> There are nine PDFs. Merge them four at a time, chaining each result into the next call, and tell me the final file name.

Round one merges files 1-4; round two merges that result with 5-7; round three adds the rest. The bookkeeping is exactly the kind of thing an agent does reliably — as long as you ask for the chaining explicitly.

## Same format family

All PDFs, or all DOCX. A mixed set has no defined merge. When you have both:

> Convert the Word files to PDF first, then merge everything.

That crosses two servers — [GroupDocs.Conversion]({{< ref "conversion/mcp/_index.md" >}}) then Merger — which an agent with both registered handles in one conversation.

## Check before you trust the result

Evaluation mode **trims the result to three pages**. A nine-document merge returning a three-page file is not a bug report, it is a licence check:

> What is the license status of the merger server?

[`get_license_status`]({{< ref "merger/mcp/tools-reference/get-license-status.md" >}}); see [Licensing]({{< ref "merger/mcp/getting-started/licensing.md" >}}).

## Setup

```bash
dnx GroupDocs.Merger.Mcp --yes
```

with `GROUPDOCS_MCP_STORAGE_PATH` pointing at your documents folder — [per-client config]({{< ref "merger/net/mcp/install-in-ai-clients.md" >}}) or the [installer]({{< ref "merger/mcp/getting-started/_index.md" >}}).

## Where to go next

* [Split and reassemble documents]({{< ref "merger/mcp/use-cases/split-and-reassemble-documents.md" >}}) — extraction, and how to rebuild a range.
* [Assemble a document pack]({{< ref "merger/mcp/use-cases/assemble-a-document-pack.md" >}}) — the repeatable multi-round workflow.
* [Extract pages from a folder]({{< ref "merger/mcp/use-cases/extract-pages-in-bulk.md" >}}) — one prompt, many files.
* [On-premise architecture]({{< ref "merger/mcp/use-cases/on-premise-document-merging.md" >}}) — why this beats an upload site.
