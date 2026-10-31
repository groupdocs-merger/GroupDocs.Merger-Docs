---
id: skip-loading-external-resources
url: merger/net/skip-loading-external-resources
title: Skip loading of external resources
weight: 3
description: "Learn how GroupDocs.Merger for .NET denies external resources by default, and how to allow trusted resources by absolute URI prefix or decide per resource with a handler."
keywords: external resources, Skip loading of external resources, Loading external resources, WhitelistedResources, SkipExternalResources, ExternalResourceHandler, IExternalResourceHandler, SSRF
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: True
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** does not load the external resources a document references unless you allow it.

## What are external resources?

*External resources* are content a document references instead of carrying: images, stylesheets, linked pictures and similar files. GroupDocs.Merger treats any resource that a document tries to load from a URL or from a file outside the document as external.

## Security considerations

Loading external resources from untrusted documents can pose security risks:

* **Server-Side Request Forgery (SSRF)**: a malicious document can reference internal network addresses, such as cloud metadata endpoints or `localhost` services, and make your server request them.
* **NTLM credential leaks**: a reference to a UNC path (for example `\\server\share`) can trigger automatic NTLM authentication and leak credentials.
* **Data exfiltration and tracking**: a request to an attacker's server reveals that, when and where a document was opened.
* **Local file disclosure**: a reference to a local file, such as `file:///etc/passwd`, can pull content from the machine into the output.

To mitigate these risks, GroupDocs.Merger is **secure by default**: every [LoadOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/loadoptions/) constructor sets `SkipExternalResources` to `true`, and a [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/) created without load options uses the same default, so nothing external is loaded unless you allow it.

## What loads by default

With `SkipExternalResources` set to `true` (the default), a document still loads:

* content it carries: `data:` URIs, `cid:` references, MHTML parts and packaged media, such as the images inside a DOCX, PPTX or EPUB file;
* resources that match an entry of `WhitelistedResources`.

Everything else is skipped and the operation continues: `http`, `https`, `ftp` and every other scheme, UNC paths, local files, including files in the document's own folder, and relative references that point outside the document.

The options are read when the `Merger` is created. Changing them afterwards does not affect that `Merger`. Documents you join to a `Merger` follow the options of that `Merger`.

{{< alert style="info" >}}
Since version 26.10, external resources are denied by default, and `LoadOptions` has the `SkipExternalResources`, `WhitelistedResources` and `ExternalResourceHandler` properties. Earlier versions loaded the external resources a document referenced and had no option to stop it. If your documents rely on remote images or stylesheets, allow their locations with `WhitelistedResources`, or set `SkipExternalResources` to `false` for documents you trust.
{{< /alert >}}

## Supported document types

`LoadOptions` implements the [IResourceLoadingOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/iresourceloadingoptions/) interface, which defines `SkipExternalResources`, `WhitelistedResources` and `ExternalResourceHandler`. GroupDocs.Merger has one `LoadOptions` class for every format, and the options take effect for these documents:

| Documents | External resources they can reference |
|-----------|---------------------------------------|
| Word processing: DOC, DOCX, DOCM, DOT, DOTX, DOTM, RTF, ODT, OTT | Linked images and other linked files |
| Web: HTML, MHT, MHTML | Images, stylesheets and other resources |
| Presentations: PPT, PPTX, PPS, PPSX, PPTM, PPSM, POTM, POTX, ODP, OTP | Linked pictures and media |
| Spreadsheets: XLS, XLSX, XLSB, XLSM, XLT, XLTX, XLTM, XLAM, ODS | Linked pictures |
| SVG, SVGZ | Images and stylesheets the drawing references |
| EPUB | Images, stylesheets and other resources from outside the book |

Other formats:

* Raster images and audio have no way to reference an external resource.
* For PDF, Visio diagrams, OneNote, plain text, CSV, and ZIP and TAR archives, the product's tests process a probe document full of external references with every operation that applies to it and observe no request.
* XPS, PostScript and TeX documents and the other archive formats are not covered by that measurement.

If you pass your own implementation of `ILoadOptions` to `Merger`, implement `IResourceLoadingOptions` as well to set these options; otherwise the defaults apply.

## Allowing trusted resources

To load particular resources from trusted locations while everything else stays denied, add their **absolute URI prefixes** to `WhitelistedResources`. The whitelist takes effect only while `SkipExternalResources` is `true`.

A resource matches an entry when:

* its scheme and host equal the entry's, ignoring case, with no subdomain matching;
* its port equals the entry's once the scheme's default port is filled in;
* its path starts with the entry's path at a `/` boundary, case-sensitively, so `/assets` does not match `/assetsX`.

Local and UNC paths are compared as `file:` URIs, so `C:\assets\logo.png` is compared as `file:///C:/assets/logo.png`. Dot segments are removed, and the query and fragment are ignored. A resource holding an encoded `/`, `\` or `.` never matches, and a relative or protocol-relative (`//host/...`) reference never matches an `http` or `https` entry.

The following example loads images and stylesheets from one CDN folder and from one local folder, and denies everything else:

```csharp
LoadOptions loadOptions = new LoadOptions(FileType.HTML)
{
    WhitelistedResources = new List<string>
    {
        "https://cdn.example.com/assets/",
        "file:///C:/assets/"
    }
};

using (Merger merger = new Merger(@"c:\sample1.html", loadOptions))
{
    merger.Join(@"c:\sample2.html");
    merger.Save(@"c:\result.html");
}
```

An entry that is null, empty, not an absolute URI, carries a query or fragment, or contains `%2F`, `%5C` or `%2E` makes the `Merger` constructor throw `ArgumentException`, whatever `SkipExternalResources` is set to:

```
Whitelisted resource '<entry>' must be an absolute URI without a query, fragment or encoded '/', '\' or '.'.
```

Keep in mind:

* the document follows redirects: a whitelisted URL that redirects loads the redirect target, even when the target is not whitelisted;
* the list is copied when the `Merger` is created, and a null list counts as empty.

To decide per resource in code, for example by file type, use a [handler](#deciding-per-resource-with-a-handler).

## Deciding per resource with a handler

When a list of prefixes is not enough — to allow resources by file type, to record every resource a document references, or to supply a resource's content yourself — set the `ExternalResourceHandler` property of `LoadOptions` to your implementation of [IExternalResourceHandler](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/iexternalresourcehandler/). The property is `null` by default.

For each external resource a document is about to load:

1. `SkipExternalResources` and `WhitelistedResources` decide first, as described above.
2. The handler's `OnLoading` method is called with an [ExternalResourceLoadingArgs](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/externalresourceloadingargs/). Its `Uri` property holds the reference, and `Skipped` holds the decision from step 1.
3. The handler can keep that decision, set `Skipped` to `false` to load the resource, set it to `true` to skip it, or set `Data` to supply the resource's content. When `Data` is set and `Skipped` is `false`, the document uses those bytes and no request is made for the resource; an empty array supplies empty content.

### Allowing images by file type

The following handler loads JPEG images from one trusted host in addition to what the defaults allow. Everything else keeps the decision of step 1, so content the document carries still loads.

```csharp
public class TrustedJpegHandler : IExternalResourceHandler
{
    public void OnLoading(ExternalResourceLoadingArgs args)
    {
        Uri uri;
        if (Uri.TryCreate(args.Uri, UriKind.Absolute, out uri)
            && uri.Scheme == Uri.UriSchemeHttps
            && string.Equals(uri.Host, "cdn.example.com", StringComparison.OrdinalIgnoreCase)
            && (uri.AbsolutePath.EndsWith(".jpg", StringComparison.OrdinalIgnoreCase)
                || uri.AbsolutePath.EndsWith(".jpeg", StringComparison.OrdinalIgnoreCase)))
        {
            args.Skipped = false;
        }
    }
}
```

```csharp
LoadOptions loadOptions = new LoadOptions(FileType.DOCX)
{
    ExternalResourceHandler = new TrustedJpegHandler()
};

using (Merger merger = new Merger(@"c:\sample1.docx", loadOptions))
{
    merger.Join(@"c:\sample2.docx");
    merger.Save(@"c:\result.docx");
}
```

Check the location as well as the file type. A URL that ends in `.jpg` can point at any server, including `http://169.254.169.254/image.jpg`, and says nothing about the content it returns.

### Supplying content and recording resources

The following handler supplies resources from content you have already downloaded and verified, and records the decision for every resource:

```csharp
public class PrefetchedResourceHandler : IExternalResourceHandler
{
    private readonly IReadOnlyDictionary<string, byte[]> _prefetched;

    public PrefetchedResourceHandler(IReadOnlyDictionary<string, byte[]> prefetched)
    {
        _prefetched = prefetched;
    }

    public void OnLoading(ExternalResourceLoadingArgs args)
    {
        byte[] content;
        if (_prefetched.TryGetValue(args.Uri, out content))
        {
            args.Data = content;
            args.Skipped = false;
        }
        Console.WriteLine("{0}: {1}", args.Skipped ? "skipped" : "loaded", args.Uri);
    }
}
```

### Rules for handlers

* For word processing, HTML and MHTML documents, `Uri` is resolved against the document's base, so it is the URL that would be requested. For other formats it can be the reference as the document carries it, so it can be relative.
* The handler is also called for content the document carries, such as `data:` URIs and `cid:` parts, with `Skipped` set to `false`. Skipping such a resource removes it from the output.
* If the handler throws, that resource is skipped, and the operation throws [GroupDocsMergerException](https://reference.groupdocs.com/merger/net/groupdocs.merger.exceptions/groupdocsmergerexception/) with your exception as `InnerException`.
* The handler can be called from several threads at once, so it must be thread-safe.
* A handler that allows everything reopens every request the defaults deny. Decide from the URI, never from content of the document being processed.

## Loading all external resources

If you process only documents you trust, you can allow every external resource by setting `SkipExternalResources` to `false`. Local files and UNC paths then load as well, the whitelist has no effect, and the document follows redirects. A [handler](#deciding-per-resource-with-a-handler), when set, is still called and can skip resources.

```csharp
LoadOptions loadOptions = new LoadOptions(FileType.DOCX)
{
    SkipExternalResources = false
};

using (Merger merger = new Merger(@"c:\trusted-document1.docx", loadOptions))
{
    merger.Join(@"c:\trusted-document2.docx");
    merger.Save(@"c:\result.docx");
}
```

## Format-specific behaviour

### EPUB, SVG and SVGZ documents

For EPUB documents, and for SVG and SVGZ documents in some operations, GroupDocs.Merger reads the document's markup to find its external references before the document is processed. That markup must be well-formed XML. If it cannot be read, the operation fails with `GroupDocsMergerException` and this message:

```
The document's markup could not be read to check it for external resources, so it was not loaded. Set SkipExternalResources to false without an ExternalResourceHandler to load it without the check.
```

To process such a document, set `SkipExternalResources` to `false` and leave `ExternalResourceHandler` unset; the markup is then not checked.

### Embedded objects

The constructors of [OleDiagramOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/olediagramoptions/), [OleSpreadsheetOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/olespreadsheetoptions/) and [OleWordProcessingOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/olewordprocessingoptions/) that take only a file path and a page number render the image of the embedded object when they are called, before any `Merger` exists. That image never shows the external resources the embedded document references, whatever the `LoadOptions` of the target document allow. To show them, render the image yourself and pass it to the constructor that takes the image data. See [Import documents]({{< ref "merger/net/developer-guide/import-documents/_index.md" >}}).

### GroupDocs.Merger.LowCode

The single-purpose products of the `GroupDocs.Merger.LowCode` package, such as `JoinPdf` or `SplitDocx`, always deny external resources and have no option to allow them.

## See also

* [Network access and data privacy]({{< ref "merger/net/getting-started/network-access-and-data-privacy.md" >}})
* [Load password-protected document]({{< ref "merger/net/developer-guide/loading/load-password-protected-document.md" >}})
