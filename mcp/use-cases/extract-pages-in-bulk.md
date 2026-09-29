---
id: mcp-uc-extract-pages-in-bulk
url: merger/mcp/use-cases/extract-pages-in-bulk
title: How to extract pages from many documents at once
linkTitle: Extract pages in bulk
weight: 4
description: "Extract the same pages from many documents in one prompt with an AI agent over MCP, and collect the results into one place."
keywords: bulk extract pages PDF, first page from every document AI, batch split documents MCP, collect signature pages
productName: GroupDocs.Merger MCP Server
toc: True
structuredData:
    showOrganization: True
    howTo:
        name: "How to extract pages from many documents at once"
        description: "Extract the same pages from many documents in one prompt with an AI agent over MCP, and collect the results into one place."
        steps:
        - name: "Install the server"
          text: "Run the GroupDocs.Merger MCP server with Docker or dnx and register it in your AI client."
        - name: "Put the documents in the storage folder"
          text: "Point GROUPDOCS_MCP_STORAGE_PATH at the folder that holds the files the agent should use."
        - name: "Ask the agent"
          text: "Extract page 1 from every PDF in my documents folder and list what you produced."
---

"Get me the first page of every one of these" is a folder-sized task that takes one prompt.

{{< alert style="info" >}}
The commands and config snippets on this page are for the **.NET** build of the server — the only platform available today. Installation and client setup: [MCP server for .NET]({{< ref "merger/net/mcp/_index.md" >}}). Other platforms will expose the same tools with their own launch command; everything else on this page applies unchanged.
{{< /alert >}}

## Setup

Point `GROUPDOCS_MCP_STORAGE_PATH` at the folder ([configuration]({{< ref "merger/net/mcp/configuration.md" >}})). Files are resolved by name, so the agent passes `invoice-014.pdf`, not a path from your machine.

## The prompt

> Extract page 1 from every PDF in my documents folder and list what you produced.

The agent calls [`split`]({{< ref "merger/mcp/tools-reference/split.md" >}}) per file. Each call writes a single-page document, so a folder of 40 invoices yields 40 cover pages.

## Variations that come up

> Extract the last page of each document — check the page count first.
> Pull page 2 out of every contract, then merge all of them into one review file.
> For each file, extract the signature page and put the results in the output folder.

The second one chains straight into [`merge`]({{< ref "merger/mcp/tools-reference/merge.md" >}}) in rounds of four — a single combined document from one page of each source.

## Ask for the page count when the position is relative

"The last page" is a different number in every file. Have the agent call [`get_document_info`]({{< ref "merger/mcp/tools-reference/get-document-info.md" >}}) per document first; an agent that guesses will fail on the files where the guess is wrong, and the error is per file rather than fatal.

## Keep the output separate

Forty extracted pages beside forty originals is a folder nobody can navigate. Set `GROUPDOCS_MCP_OUTPUT_PATH` to a distinct directory ([configuration]({{< ref "merger/net/mcp/configuration.md" >}})) so results land apart from sources.

## Practical notes

* **Failures are per file.** A corrupt or password-protected document fails its own call; ask for the failures as a list so a batch of 40 does not hide two errors.
* **Metered usage adds up.** Under [metered licensing]({{< ref "merger/mcp/getting-started/licensing.md" >}}#metered-pay-per-use-licensing) every call is billed processing.
* **Evaluation mode trims merged output to three pages** — extraction of single pages is unaffected, but the moment you merge the results, the cap applies.
