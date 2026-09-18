---
id: mcp-uc-on-premise-document-merging
url: merger/mcp/use-cases/on-premise-document-merging
title: "Running GroupDocs MCP servers on-premise: architecture and security model"
linkTitle: On-premise deployment
weight: 5
description: "Run document merging and splitting for AI agents fully on-premise: local stdio transport, no external endpoints, no inbound ports, no telemetry."
keywords: on-premise MCP server, air-gapped document merging, MCP security model, local PDF merge no upload
productName: GroupDocs.Merger MCP Server
toc: True
structuredData:
    showOrganization: True
    howTo:
        name: "Running GroupDocs MCP servers on-premise: architecture and security model"
        description: "Run document merging and splitting for AI agents fully on-premise: local stdio transport, no external endpoints, no inbound ports, no telemetry."
        steps:
        - name: "Run the pinned image inside the perimeter"
          text: "Start the GroupDocs.Merger MCP server from its versioned Docker image as a child process of the AI client."
        - name: "Mount only the folders the agent may reach"
          text: "Map the document folder read-write and the license folder read-only."
        - name: "Choose the license mode"
          text: "Use a license file for fully offline operation; metered licensing needs outbound egress for usage reports."
---

Run merging and splitting for AI agents **fully on-premise**: the GroupDocs.Merger MCP server uses local stdio transport with **no external endpoints, no inbound ports, and no telemetry**. This page is the one to send your security reviewer.

{{< alert style="info" >}}
The commands and config snippets on this page are for the **.NET** build of the server — the only platform available today. Installation and client setup: [MCP server for .NET]({{< ref "merger/net/mcp/_index.md" >}}). Other platforms will expose the same tools with their own launch command; everything else on this page applies unchanged.
{{< /alert >}}

## The architecture in one picture

```text
+--------------+          +--------------------+         +------------------+
|  AI client   |  stdio   | MCP server process | reads / | local filesystem |
| (Claude, VS  | <----->  | (GroupDocs engine) | <-----> | storage / output |
| Code, agent) | JSON-RPC |   child process    |  writes |     folders      |
+--------------+          +--------------------+         +------------------+
```

* **Transport:** the AI client *starts the server as a child process* and communicates over standard input/output. The server never listens on a network socket.
* **Data path:** agent → local server → local filesystem. Sources and results are read and written in the folders you configure; no document content is transmitted anywhere.
* **Network use:** only at install time (nuget.org or ghcr.io/docker.io). At runtime the server makes no outbound calls. Air-gapped: pre-pull the image or pre-cache the package and pin the version.
* **Telemetry:** none. The engine processes documents in-process.

## The comparison that matters

Every free "merge PDF" site works the same way: you upload both documents to someone else's server, they merge them, you download the result. For a personal receipt that is fine. For a board pack, a patient record, or a tender response it is a data transfer to a third party, usually with no record of it.

This server is the same capability with the transfer removed. The documents never leave the machine; the only thing that travels is the conversation with your model — file names, page counts, and whatever the agent says back. With a locally-hosted model, not even that.

## Docker deployment inside the perimeter

```bash
docker run --rm -i \
  -v /srv/documents:/data \
  -v /srv/licenses:/license:ro \
  -e GROUPDOCS_MCP_STORAGE_PATH=/data \
  -e GROUPDOCS_MCP_OUTPUT_PATH=/data/assembled \
  -e GROUPDOCS_LICENSE_PATH=/license/GroupDocs.Merger.lic \
  ghcr.io/groupdocs-merger/merger-net-mcp:26.9.0
```

* Pin the tag (`:26.9.0`, not `:latest`).
* A separate output path keeps assembled packs away from the parts.
* Licence read-only; mount only the folders the agent should reach.

## License management

* **License file** — read from local disk by the local process. Fully offline; the right answer for air-gapped deployments, and the only way to avoid the three-page trim.
* **Metered (pay-per-use)** — reports *usage* to GroupDocs servers, so it needs outbound egress. Document content is never part of that report.

Both are covered in [Licensing]({{< ref "merger/mcp/getting-started/licensing.md" >}}).

## What this fits — honestly

**A good fit:** assembling packs and bundles from parts, extracting pages at scale, and doing both inside a network that does not permit document uploads.

**Not what this is:** a document editor. It combines and extracts whole pages; it does not reorder pages inside a file, insert a page at a position, or edit content. Some of those can be built from extract-then-merge sequences; others belong to the library API rather than these four tools.

## FAQ

**Does any document content leave the machine?** No. Merging and splitting happen in-process against local files.

**Does it need internet at runtime?** No — only at install, and when metered licensing is enabled.

**Can I run it air-gapped?** Yes: pre-pull the image, use a license file, pin the version.

**What ports does it open?** None. stdio only.

**How do I prove that?** The [verification script]({{< ref "merger/net/mcp/troubleshooting.md" >}}#verifying-an-installation-end-to-end) performs a real handshake and a real engine call so you can watch exactly what happens.
