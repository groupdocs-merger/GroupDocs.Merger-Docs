---
id: mcp-uc-assemble-a-document-pack
url: merger/mcp/use-cases/assemble-a-document-pack
title: How to assemble a document pack with an AI agent
linkTitle: Assemble a document pack
weight: 3
description: "Assemble a multi-part document pack with an AI agent over MCP: merge in rounds, keep the order, and produce one file for distribution."
keywords: assemble document pack AI, combine report sections agent, merge many PDFs rounds, build tender pack MCP
productName: GroupDocs.Merger MCP Server
toc: True
structuredData:
    showOrganization: True
    howTo:
        name: "How to assemble a document pack with an AI agent"
        description: "Assemble a multi-part document pack with an AI agent over MCP: merge in rounds, keep the order, and produce one file for distribution."
        steps:
        - name: "Install the server"
          text: "Run the GroupDocs.Merger MCP server with Docker or dnx and register it in your AI client."
        - name: "Put the documents in the storage folder"
          text: "Point GROUPDOCS_MCP_STORAGE_PATH at the folder that holds the files the agent should use."
        - name: "Ask the agent"
          text: "Merge every PDF in my documents folder into one pack, in file-name order. Merge four at a time, chaining each result into the next call, and tell me the final file name."
---

Tender packs, board papers, case bundles, onboarding packets: the same shape every time — a fixed order, more than four parts, and a deadline. This is the workflow.

{{< alert style="info" >}}
The commands and config snippets on this page are for the **.NET** build of the server — the only platform available today. Installation and client setup: [MCP server for .NET]({{< ref "merger/net/mcp/_index.md" >}}). Other platforms will expose the same tools with their own launch command; everything else on this page applies unchanged.
{{< /alert >}}

## Name the files so order is obvious

```text
D:/Storage/Documents/
  00-cover.pdf
  01-summary.pdf
  02-body.pdf
  03-appendix-a.pdf
  04-appendix-b.pdf
  05-annexes.pdf
```

A numeric prefix removes all ambiguity about sequence — for you and for the agent.

## The prompt

> Merge every PDF in my documents folder into one pack, in file-name order. Merge four at a time, chaining each result into the next call, and tell me the final file name.

The agent runs [`merge`]({{< ref "merger/mcp/tools-reference/merge.md" >}}) in rounds: 00-03 → result, result + 04-05 → final. Two calls here; more parts simply mean more rounds.

## Verify before you send

> How many pages does the final pack have?

[`get_document_info`]({{< ref "merger/mcp/tools-reference/get-document-info.md" >}}) on the result, compared against the sum of the parts, is a two-second check that catches the two failure modes that matter: a part silently missing, and the **three-page evaluation trim**. A pack that should be 87 pages and reports 3 was produced unlicensed — [`get_license_status`]({{< ref "merger/mcp/tools-reference/get-license-status.md" >}}).

## When the parts are not all PDFs

Convert first, then assemble:

> Convert the Word sections to PDF, then merge everything in file-name order.

With both the [Conversion]({{< ref "conversion/mcp/_index.md" >}}) and Merger servers registered, that is one conversation.

## Finishing touches other servers provide

A pack usually needs more than assembly:

* **Mark it** — a CONFIDENTIAL or DRAFT watermark: [GroupDocs.Watermark]({{< ref "watermark/mcp/_index.md" >}}).
* **Sign it** — a digital signature on the final file: [GroupDocs.Signature]({{< ref "signature/mcp/_index.md" >}}).
* **Clean it** — strip metadata before it leaves: [GroupDocs.Metadata]({{< ref "metadata/mcp/_index.md" >}}).

Each is a separate server with the same install pattern, and an agent that has them all can run the whole sequence from one prompt — locally, in the right order, with the file names it produced at each step.
