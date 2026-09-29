---
id: mcp-uc-split-and-reassemble-documents
url: merger/mcp/use-cases/split-and-reassemble-documents
title: How to split a document and reassemble the pages you want
linkTitle: Split and reassemble
weight: 2
description: "Extract pages from a document with an AI agent over MCP and reassemble a subset into a single file by chaining split and merge."
keywords: split PDF pages AI agent, extract pages MCP, reassemble document pages, remove page from PDF agent
productName: GroupDocs.Merger MCP Server
toc: True
structuredData:
    showOrganization: True
    howTo:
        name: "How to split a document and reassemble the pages you want"
        description: "Extract pages from a document with an AI agent over MCP and reassemble a subset into a single file by chaining split and merge."
        steps:
        - name: "Install the server"
          text: "Run the GroupDocs.Merger MCP server with Docker or dnx and register it in your AI client."
        - name: "Put the documents in the storage folder"
          text: "Point GROUPDOCS_MCP_STORAGE_PATH at the folder that holds the files the agent should use."
        - name: "Ask the agent"
          text: "Pull out pages 3, 6, and 8 of report.pdf."
---

[`split`]({{< ref "merger/mcp/tools-reference/split.md" >}}) extracts the pages you name, **each as its own document**. That is the detail that shapes every workflow here: three page numbers produce three files, not one file with three pages.

{{< alert style="info" >}}
The commands and config snippets on this page are for the **.NET** build of the server — the only platform available today. Installation and client setup: [MCP server for .NET]({{< ref "merger/net/mcp/_index.md" >}}). Other platforms will expose the same tools with their own launch command; everything else on this page applies unchanged.
{{< /alert >}}

## Extracting

> Pull out pages 3, 6, and 8 of report.pdf.

Three single-page documents land in your output folder. Perfect when each page is the deliverable — a signature page, a certificate, one form from a bundle.

## Getting a range back

To end up with **one** document containing those pages, extract and then merge:

> Extract pages 3, 6 and 8, then merge the three results into one file in that order.

Two tool families, one prompt. The agent chains [`split`]({{< ref "merger/mcp/tools-reference/split.md" >}}) into [`merge`]({{< ref "merger/mcp/tools-reference/merge.md" >}}) — remembering that merge takes at most four inputs per call, so a long range needs rounds.

## Removing a page

The same trick, inverted:

> This document has 10 pages. Extract all of them except page 4, then merge the rest back together in order.

Ask for the page count first ([`get_document_info`]({{< ref "merger/mcp/tools-reference/get-document-info.md" >}})) so the agent enumerates the right list rather than guessing at the length.

## Know the page count before you ask

Requesting page 12 of a ten-page document fails — correctly, but it wastes a round trip:

> How many pages does this have? Then extract the last three.

## Spreadsheets split by worksheet

In spreadsheet formats the page numbers address **worksheets**, not printed pages. *"Split out sheet 2"* is `pages: "2"`, and the result is a workbook containing that sheet.

## The evaluation limit shows up here too

A reassembled document is subject to the same three-page trim as any other merge output. If a rebuilt eight-page range comes back as three, check [`get_license_status`]({{< ref "merger/mcp/tools-reference/get-license-status.md" >}}) before looking for a bug.
