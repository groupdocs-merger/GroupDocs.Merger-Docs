---
id: merge-untrusted-documents-safely
url: merger/net/getting-started/use-cases/merge-untrusted-documents-safely
title: Merge Untrusted HTML Documents Safely in .NET
weight: 502
description: "Four ways to control which external resources GroupDocs.Merger for .NET loads when merging untrusted HTML uploads, compared side by side: the 26.10 secure defaults, a trusted-asset handler, WhitelistedResources prefixes, and SkipExternalResources for documents you already trust."
keywords: GroupDocs.Merger, .NET, C#, merge HTML documents, untrusted uploads, SSRF, external resources, IExternalResourceHandler, WhitelistedResources, LoadOptions, secure document merging, data leak prevention
productName: GroupDocs.Merger for .NET
structuredData:
    showOrganization: True
toc: true
hideChildren: False
---

**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** gives a merge pipeline four distinct ways to treat the external resources an HTML upload references, and picking among them is a decision worth making on purpose.

{{< alert style="info" >}}
💡 Full working example available on GitHub:
[merge-untrusted-html-uploads-dotnet](https://github.com/groupdocs-merger/merge-untrusted-html-uploads-dotnet)
{{< /alert >}}

## Introduction

Securing an HTML merge against untrusted uploads is a GroupDocs.Merger setting for .NET that decides which external resources a joined document may reach, and GroupDocs.Merger for .NET exposes four such settings rather than one. A merge step joining HTML from an upload portal or a multi-tenant backend inherits whatever that HTML asks for unless something stops it, and these four options differ in exactly what each stops. This page sets them side by side using the same invoice and delivery-note uploads, judged by what each lets through, how much configuration it needs, and what already has to be true about the document.

## What This Guide Covers

This guide compares the 26.10 secure defaults, a per-resource `IExternalResourceHandler`, `WhitelistedResources` prefix matching, and `SkipExternalResources = false`, using the sample project's methods and shared handler class.

**Prerequisites:**
- GroupDocs.Merger for .NET 26.10 or later (the behavior compared here is new in that release)
- Two or more HTML documents to join, at least one from a source you do not fully control

## Installation

```bash
dotnet add package GroupDocs.Merger --version 26.10.0
```

Also listed on [NuGet.org](https://www.nuget.org/packages/GroupDocs.Merger/). No license is required; an unlicensed `Merger` makes the same decisions as a licensed one, but adds an evaluation notice to each joined document.

## Repository Structure

```
merge-untrusted-html-uploads-dotnet/
├── Program.cs
├── UntrustedMergeDemo.csproj
└── resources/
    ├── brand/logo.png
    └── uploads/
        ├── delivery-note-upload.html
        ├── invoice-upload.html
        └── other-customer-signature.jpg
```

`Program.cs` holds the three documented methods below, plus the `ResourceAudit` class
([Program.cs, lines 172-207](https://github.com/groupdocs-merger/merge-untrusted-html-uploads-dotnet/blob/main/Program.cs#L172-L207))
that implements `IExternalResourceHandler` for two of them.

## Quick Decision Matrix

| Scenario | Recommended Option | Why |
|---|---|---|
| Arbitrary customer uploads, no exceptions needed | Secure defaults alone | Nothing external loads; no setup beyond the format |
| One brand asset, such as a logo, must render | Trusted-asset handler | Supplies bytes for one reference, denying the rest |
| A whole trusted source must reach every upload | `WhitelistedResources` prefix | Covers an absolute URI prefix, no handler code |
| Every document reaching this `Merger` is already trusted | `SkipExternalResources = false` | Loads everything, local files and UNC paths included |

## Detailed Method Analysis

### Method 1: Secure Defaults Alone

**Overview:** since 26.10, every `LoadOptions` constructor sets `SkipExternalResources = true`, as does a `Merger` without load options, so `new LoadOptions(FileType.HTML)` alone denies every external reference the uploads carry; options are read once, at construction, and inherited by any joined document.

#### Does a Same-Folder Reference Get Any Special Treatment?

No. The default decision for a reference is already settled by the time the handler sees `args.Uri`. A path such as `other-customer-signature.jpg` is evaluated like any other reference: the rule looks at what a reference names, not how near it is to the document.

**When to use:** no reason to fetch anything external, from documents your own code does not control; not when one external asset legitimately needs to render.

```csharp
var audit = new ResourceAudit();
var loadOptions = new LoadOptions(FileType.HTML) { ExternalResourceHandler = audit };
```

```csharp
using (var merger = new Merger(firstUpload, loadOptions))
{
    merger.Join(secondUpload);
    merger.Save(outputPath);
}
```

We joined the invoice and delivery-note uploads with just this option set, and all seven external references came back blocked: the remote stylesheet, the remote logo, the cloud-metadata URL, the relative reference beside the invoice, a `file:///` path, a UNC path, and the tracking pixel with a query string. None loaded, and the logo's own placeholder kept the alt text "Company logo".

**Pros and cons:** zero configuration, but it blocks assets you might want and gives no visibility into what it blocked.

### Method 2: Trusted-Asset Handler

**Overview:** a handler lets one or a few references through, from bytes you already hold, while the rest of the join keeps denying everything else.

`OnLoading` receives an `ExternalResourceLoadingArgs` carrying the requested `Uri`, a `Skipped` flag already holding the default decision, and a writable `Data` property; setting `Skipped = false` and `Data` to a byte array answers the request with no network call. `ResourceAudit` can run on several threads per join, recording decisions in `ConcurrentQueue<string>`.

**When to use:** one or a few specific resources must render while everything else stays denied; not for a trusted-resource list that would keep growing.

```csharp
var trustedAssets = new Dictionary<string, byte[]>
{
    [logoUrl] = File.ReadAllBytes(logoPath)
};
var audit = new ResourceAudit(trustedAssets);
var loadOptions = new LoadOptions(FileType.HTML) { ExternalResourceHandler = audit };
```

```csharp
using (var merger = new Merger(firstUpload, loadOptions))
{
    merger.Join(secondUpload);
    merger.Save(outputPath);
}
```

When we reran the join with this handler attached, the logo came back `supplied` and the other six references stayed `blocked`, with the logo embedded as image data rather than a placeholder.

**Pros and cons:** grants access per resource, not per document, but needs handler logic; a throwing `OnLoading` skips that resource and fails the whole operation with `GroupDocsMergerException`, wrapping the handler's exception as its `InnerException`.

### Method 3: `WhitelistedResources` Prefix

**Overview:** a whitelist entry grants everything under one trusted absolute URI prefix without any handler code, as long as the prefix is well formed.

`WhitelistedResources` takes absolute URI prefixes, such as `https://cdn.example.com/brand/`, matched by scheme, host and port (ignoring case) and by a path prefix at a `/` boundary (case-sensitively), and only while `SkipExternalResources` is `true`. A malformed entry, a bare host name among them, throws `ArgumentException` at construction; a redirect from a whitelisted URL still loads its target.

**When to use:** a whole trusted CDN prefix should reach every upload, when a list beats handler code; not for one ad hoc resource outside a stable prefix.

```csharp
var loadOptions = new LoadOptions(FileType.HTML)
{
    WhitelistedResources = new List<string> { entry }
};
```

```csharp
try
{
    using var merger = new Merger(uploadPath, loadOptions);
    merger.Save(ResultPath("loose-whitelist.html"));
    return null;
}
catch (ArgumentException exception)
{
    Console.WriteLine($"   {exception.Message}");
    return exception.Message;
}
```

Passing `"cdn.example.com"`, a bare host name rather than an absolute URI prefix, produced this exact message when we ran it:

```
Whitelisted resource 'cdn.example.com' must be an absolute URI without a query, fragment or encoded '/', '\' or '.'. (Parameter 'WhitelistedResources')
```

**Pros and cons:** covers a trusted prefix with no per-request code and fails at construction, but it grants everything under that prefix, with a redirect followed unchecked.

### Method 4: `SkipExternalResources = false`

**Overview:** turning the default off loads every external resource, local files and UNC paths included, instead of denying it; it applies to the whole `Merger` and is all-or-nothing, not scoped to a resource or a prefix.

**When to use:** every document reaching this `Merger` is already fully trusted; not for anything from an upload, a customer, or another tenant.

```csharp
var loadOptions = new LoadOptions(FileType.HTML) { SkipExternalResources = false };
```

**Pros and cons:** one property, with no handler or whitelist to maintain, but it reopens local and UNC access with no way to deny some references while allowing others.

## Real-World Use Cases

**Invoice and delivery-note consolidation:** a portal joins two HTML uploads from the same order, neither written by its own team; secure defaults deny every external reference with no configuration.

**A service that must render its own logo:** the HTML comes from outside parties, but one brand asset still has to render; a handler supplies the logo's bytes directly, with no network request, while everything else stays denied.

**Joining documents the pipeline already produced:** a later stage joins HTML the same trusted system generated earlier, whose images and stylesheets are meant to load; `SkipExternalResources = false`, scoped to that stage alone, allows that without touching the defaults used for customer uploads.

## Common Pitfalls and How to Avoid Them

1. **Assuming a relative path is safe inside the upload's folder.** `other-customer-signature.jpg` looks harmless, but the defaults deny it like a remote URL.

2. **Writing a whitelist entry as a bare host name.** `cdn.example.com` throws `ArgumentException` at construction; use a full prefix, such as `https://cdn.example.com/brand/`.

3. **Treating `IExternalResourceHandler` as single-threaded.** `OnLoading` can run on several threads at once, so shared state needs `ConcurrentQueue<string>`, as `ResourceAudit` shows.

## Migration Guide

### Before GroupDocs.Merger 26.10

Earlier versions loaded the external resources an HTML document referenced, with no option to stop it. Verified against an absolute `file:///` reference: before 26.10, it loaded, and its file was embedded in the merged output. A relative, same-folder reference was not loaded before 26.10 either; the 26.10 change is the default for every reference, not a gap unique to relative paths.

## FAQ

**Can these four options be combined on the same `Merger`?**
Partly: `WhitelistedResources` and a handler share one `LoadOptions`, and `OnLoading` runs after the whitelist decision is already in `args.Skipped`; the whitelist itself has no effect once `SkipExternalResources` is `false`.

**Does the same policy apply to formats other than HTML?**
Yes, word processing, HTML/MHTML, presentations, spreadsheets, SVG and EPUB all honor the same `LoadOptions` settings.

**What about content a document already carries internally, like media inside a DOCX or PPTX file?**
It is unaffected; only resources referenced from outside the document get the default, whitelist, or handler decision.

## Conclusion

None of these four options is universally right; the choice depends on what the pipeline is supposed to trust, not on which is newest. The 26.10 defaults suit an outside upload; a handler narrows the denial to the one or two assets actually needed; a whitelist prefix covers a whole trusted source with no handler code; `SkipExternalResources = false` belongs only where the whole document is already known safe. GroupDocs.Merger for .NET leaves that trust decision with the caller.

## See Also

- [In-depth blog article about this project](https://blog.groupdocs.com/merger/merge-untrusted-documents-safely-net/) - the before/after story behind GroupDocs.Merger 26.10
- [Skip Loading External Resources](https://docs.groupdocs.com/merger/net/skip-loading-external-resources/) - the format table and full rules these defaults are based on
- [Network Access and Data Privacy](https://docs.groupdocs.com/merger/net/network-access-and-data-privacy/) - when GroupDocs.Merger accesses the network and what never leaves your machine
- [LoadOptions API reference](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/loadoptions/)
- [IExternalResourceHandler API reference](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/iexternalresourcehandler/)
- [GroupDocs.Merger on NuGet.org](https://www.nuget.org/packages/GroupDocs.Merger/)
- [Full working example on GitHub](https://github.com/groupdocs-merger/merge-untrusted-html-uploads-dotnet)
