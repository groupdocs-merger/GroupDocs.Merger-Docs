---
id: merge-and-split-documents-in-one-line
url: merger/net/getting-started/use-cases/merge-and-split-documents-in-one-line
title: Merge and Split PDF, Word and PowerPoint Files in One Line of C#
weight: 501
description: "Method-by-method guide to GroupDocs.Merger.LowCode for .NET: merge PDF in one line, merge Word documents, split PDF pages and PowerPoint slides, and remove PDF pages in C#."
keywords: GroupDocs.Merger.LowCode, GroupDocs.Merger, .NET, C#, merge PDF in one line, merge Word documents, split PDF pages, split PowerPoint slides, remove PDF pages, JoinPdf, SplitPdf, low-code document merging
productName: GroupDocs.Merger for .NET
toc: true
hideChildren: False
---

**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** exposes a
general-purpose `Merger` class for complex, multi-format jobs, and ships a separate
**GroupDocs.Merger.LowCode** package for everything smaller than that. Single-purpose
document assembly is a GroupDocs.Merger capability for .NET that hands each merge,
split or page-removal job to its own LowCode product, through `JoinPdf`, `JoinDocx`,
`JoinPptx`, `SplitPdf`, `SplitDocx`, `SplitPptx` and `RemovePagesPdf`.

{{< alert style="info" >}}
💡 Full working example available on GitHub:
[one-line-document-merge-and-split-dotnet](https://github.com/groupdocs-merger/one-line-document-merge-and-split-dotnet)
{{< /alert >}}

## Overview

A developer who needs one document operation, not a document-processing platform,
usually ends up reading more of the general `Merger` API than the task requires.
GroupDocs.Merger.LowCode packages seven of those single operations as their own types,
each covering its job end to end. This guide walks through five of them in six
methods against the GroupDocs.Merger 26.10 sample and the five files it ships with:
`report.pdf`, `appendix.pdf`, `contract.docx`, `amendment.docx` and `deck.pptx`. Each
method follows the same two steps: build the product with its source and options,
then call `Save` to run it.

**What you'll learn:**
- Joining PDF files with `JoinPdf` and Word documents with `JoinDocx`
- Splitting PDF pages with `SplitPdf` and PowerPoint slides with `SplitPptx`
- Removing PDF pages with `RemovePagesPdf` without touching the source file
- What a mismatched input raises, and what changes without a license

{{< alert style="success" >}}
**Complete source code** is available in the
[GitHub repository](https://github.com/groupdocs-merger/one-line-document-merge-and-split-dotnet).
{{< /alert >}}

**Prerequisites:**
- .NET 6.0 or later (this sample's project targets net8.0)
- The separate `GroupDocs.Merger.LowCode` NuGet package
- A PDF, DOCX or PPTX input file; this guide uses the sample's own `report.pdf`,
  `contract.docx` and `deck.pptx`

**Key concepts:**
- **Constructor-then-Save** – source and options go in the constructor; the work
  happens only once `Save(outputPath)` is called.
- **Format checking** – every product checks its source and every file it is given
  against its own format before writing anything.
- **Stream or path** – all seven constructors accept their source as a file path or a
  stream, in the same constructor position.

## Why GroupDocs.Merger.LowCode Isn't the Full Merger Class

Each LowCode product wraps one `Merger` operation and stops there.

Move to the full [GroupDocs.Merger API](https://reference.groupdocs.com/merger/net/)
when a task needs:

- a join across two different formats, not just two files of the same one
- a page-level option on the join itself, beyond the whole-document append every
  LowCode join performs
- the result written to a stream instead of a file path
- information about a document before deciding what to do with it

## Repository Structure

```
one-line-document-merge-and-split-dotnet/
├── OneLineMergeDemo.csproj
├── Program.cs
└── resources/
    ├── amendment.docx
    ├── appendix.pdf
    ├── contract.docx
    ├── deck.pptx
    └── report.pdf
```

`Program.cs` holds the six methods below; `resources/` holds the five files they
operate on.

## Method 1: Joining Two PDF Files

**Format:** PDF | **Product:** `JoinPdf` | **Best For:** appending a cover page or an
appendix to a report before archiving it

`JoinPdf` takes the source PDF, the files to append, and a `JoinOptions` instance in
its constructor. Every file passed in must already be a PDF, or the call throws
`FileTypeNotSupportedException` instead of writing anything; `Save` creates the output
folder if it does not already exist.

```csharp
new JoinPdf(sourcePath, new[] { appendedPath }, new JoinOptions())
    .Save(outputPath);
```

In our own run, joining the sample's 2-page `report.pdf` with its 2-page
`appendix.pdf` produced a 4-page, 257987-byte `report-with-appendix.pdf`.

## Method 2: Joining Two Word Documents

**Format:** DOCX | **Product:** `JoinDocx` | **Best For:** appending a signed
amendment to a contract

`JoinDocx` follows the exact constructor-then-`Save` shape as `JoinPdf`, for Word
files: the appended document lands after the last page of the source document.

```csharp
new JoinDocx(sourcePath, new[] { appendedPath }, new JoinOptions())
    .Save(outputPath);
```

In our own run, joining the 6-page `contract.docx` with the 1-page `amendment.docx`
produced a 7-page, 7915-byte `contract-with-amendment.docx`.

## Method 3: Splitting PDF Pages

**Format:** PDF | **Product:** `SplitPdf` | **Best For:** pulling named pages out of a
report into files of their own

`SplitPdf` takes the source PDF and the page numbers to extract; `Save` writes one
file per requested page. A `{0}` token in the output name becomes the part number, so
`report-page_{0}.pdf` yields `report-page_1.pdf` and `report-page_2.pdf`; without it,
the number is appended instead.

```csharp
new SplitPdf(sourcePath, pageNumbers).Save(outputPattern);
```

Splitting pages 1 and 2 of `report.pdf` in our sample run produced `report-page_1.pdf`
and `report-page_2.pdf`, each a single page.

## Method 4: Splitting PowerPoint Slides

**Format:** PPTX | **Product:** `SplitPptx` | **Best For:** sending two slides from a
sixty-slide deck to one stakeholder

`SplitPptx` mirrors `SplitPdf` for presentation decks. Without a `{0}` token, the part
number is appended instead, so `deck-slide.pptx` becomes `deck-slide_1.pptx` and
`deck-slide_2.pptx`.

```csharp
new SplitPptx(sourcePath, slideNumbers).Save(outputPath);
```

In our sample run, splitting slides 1 and 2 of the 6-slide `deck.pptx` produced two
one-slide files, `deck-slide_1.pptx` and `deck-slide_2.pptx`.

## Method 5: Removing Pages From a PDF

**Format:** PDF | **Product:** `RemovePagesPdf` | **Best For:** dropping a page that
should never have shipped, without disturbing the original

`RemovePagesPdf` takes the source PDF and a `RemoveOptions` instance built from the
page numbers to drop; the source file is left unchanged.

```csharp
new RemovePagesPdf(sourcePath, new RemoveOptions(pageNumbers)).Save(outputPath);
```

Removing page 2 from `report.pdf` in our own run produced a 1-page, 86647-byte
`report-without-page-2.pdf`, while `report.pdf` itself stayed unchanged.

## Method 6: Catching a Mismatched Join Before It Writes Anything

**Format:** any | **Product:** `JoinPdf` (the same check applies to every join
product) | **Best For:** validating unattended input before it reaches an archive

Every LowCode product checks its source and every file it is given against its own
format before writing anything. Wrap the join in a `try`/`catch` for
`FileTypeNotSupportedException` whenever the inputs are not guaranteed to be right.

```csharp
try
{
    new JoinPdf(pdfPath, new[] { wordPath }, new JoinOptions())
        .Save(outputPath);
}
catch (FileTypeNotSupportedException exception)
{
    Console.WriteLine(exception.Message);
}
```

In the sample run, where the paths are built from its `resources` folder, the message
read: `Input format does not match the expected format 'PDF'; the joined file
'resources\contract.docx' is 'Microsoft Word Open XML Document (.docx)'.` Nothing is
written to `outputPath` when the check fails. The exception stops only the one call it
came from; a batch of several joins still needs its own loop and its own
`try`/`catch` per item.

## Choosing the Right Method

| Method | Product | Operation | Format |
|---|---|---|---|
| Method 1 | `JoinPdf` | Append a PDF to a PDF | PDF |
| Method 2 | `JoinDocx` | Append a Word document to a Word document | DOCX |
| Method 3 | `SplitPdf` | Extract chosen pages into files of their own | PDF |
| Method 4 | `SplitPptx` | Extract chosen slides into files of their own | PPTX |
| Method 5 | `RemovePagesPdf` | Drop chosen pages, leaving the source untouched | PDF |
| Method 6 | `JoinPdf` | Reject a format mismatch before writing anything | any |

## Licensing and Evaluation Mode

A static `License.Set(licensePath)` call applies a metered license file or a standard
`.lic` file for the LowCode products. Without one, the products run in
evaluation mode: in our own unlicensed run, the joined outputs from Methods 1 and 2
were cut to 3 pages each, while all six method calls still produced output.

## Frequently Asked Questions

### Does GroupDocs.Merger.LowCode replace the full GroupDocs.Merger API?

No. See "Why GroupDocs.Merger.LowCode Isn't the Full Merger Class" above for what
stays in the full API.

### What happens if I run the sample without a license?

Evaluation limits apply to every GroupDocs.Merger.LowCode product once `License.Set`
is skipped. In our own unlicensed run, the joined PDF and Word outputs from Methods 1
and 2 were cut down to 3 pages each, shorter than their licensed results of 4 and 7
pages, while every one of the six method calls above still produced an output file.
Applying a license with `License.Set` removes that limit entirely.

### Can I pass a stream instead of a file path?

Yes, in the same constructor position a file path would take; this guide uses file
paths throughout for clarity.

### What does the `{0}` token in an output name do?

When present, it is replaced with the part number, as Methods 3 and 4 show. When
absent, the part number is appended to the base name instead.

## Summary and When to Use Which Method

All six methods share one shape: build the product with its source and options, then
call `Save`. Use Method 1 or 2 to append one document to another of the same format,
Method 3 or 4 to split chosen pages or slides into files of their own, Method 5 to
drop pages without touching the source, and Method 6 to validate a join's inputs
before anything gets written. Stay with LowCode while a job is one well-defined
operation, and move up to the full GroupDocs.Merger API once it needs a cross-format
join, a page-level join option, an output stream or document information.

## See Also

- [In-depth blog article about this sample](https://blog.groupdocs.com/merger/merge-and-split-documents-in-one-line-net/) – the companion write-up, with a back-office framing of the same operations
- [GroupDocs.Merger.LowCode installation guide](https://docs.groupdocs.com/merger/net/installation/)
- [GroupDocs.Merger for .NET features overview](https://docs.groupdocs.com/merger/net/features-overview/)
- [Complete source code on GitHub](https://github.com/groupdocs-merger/one-line-document-merge-and-split-dotnet)
- [GroupDocs.Merger.LowCode on NuGet](https://www.nuget.org/packages/GroupDocs.Merger.LowCode/)
- [GroupDocs.Merger API Reference](https://reference.groupdocs.com/merger/net/) – covers the general-purpose `Merger` class, not the LowCode namespace
