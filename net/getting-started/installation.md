---
id: installation
url: merger/net/installation
title: Installation
weight: 8
description: "How to install GroupDocs.Merger for .NET using NuGet, .NET CLI, or from the official website."
keywords: GroupDocs.Merger, install, NuGet, .NET CLI, Visual Studio
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: true
---

This topic describes how to add the GroupDocs.Merger library to your .NET project.

## Install from NuGet

GroupDocs.Merger is available on NuGet. Starting from version 26.4, the main `GroupDocs.Merger` package is a meta-package that automatically pulls in the correct runtime package for your project's target framework.

### Using .NET CLI

Open a terminal in your project folder and run:

```bash
dotnet add package GroupDocs.Merger
```

### Using Package Manager Console

In Visual Studio, open **Tools** > **NuGet Package Manager** > **Package Manager Console** and run:

```powershell
Install-Package GroupDocs.Merger
```

### Using PackageReference

Add directly to your `.csproj` file, replacing `x.y.z` with the version you want to use (for example, the latest version listed on [NuGet](https://www.nuget.org/packages/GroupDocs.Merger)):

```xml
<PackageReference Include="GroupDocs.Merger" Version="x.y.z" />
```

## Runtime Packages

The `GroupDocs.Merger` package selects one of the following runtime packages based on your project's target framework:

| Target Framework                  | Runtime Package                      |
|-----------------------------------|--------------------------------------|
| .NET Framework 4.6.2              | `GroupDocs.Merger.Net462`            |
| .NET 6.0                          | `GroupDocs.Merger.Net60`             |
| .NET 8.0                          | `GroupDocs.Merger.Net80`             |
| .NET 10.0                         | `GroupDocs.Merger.Net100`            |
| .NET 6.0 for Windows (`net6.0-windows`)   | `GroupDocs.Merger.Net60.Windows`     |
| .NET 8.0 for Windows (`net8.0-windows`)   | `GroupDocs.Merger.Net80.Windows`     |
| .NET 10.0 for Windows (`net10.0-windows`) | `GroupDocs.Merger.Net100.Windows`    |

The `GroupDocs.Merger.Net60`, `GroupDocs.Merger.Net80` and `GroupDocs.Merger.Net100` packages run on Windows (x64, x86), Linux and macOS. To run on Windows ARM64, target `net6.0-windows`, `net8.0-windows` or `net10.0-windows` so that the `.Windows` runtime package is used.

In most cases, install only the main `GroupDocs.Merger` package — NuGet will resolve the correct runtime package automatically. You can also install a specific runtime package directly if needed:

```bash
dotnet add package GroupDocs.Merger.Net80
```

{{< alert style="info" >}}
**GroupDocs.Merger.LowCode** is a separate NuGet package (.NET 6.0 and later) with single-purpose products such as `JoinPdf` or `SplitDocx`. Install it only if you use those products:

```bash
dotnet add package GroupDocs.Merger.LowCode
```
{{< /alert >}}

## Download from the Official Website

You can also download the assemblies as a ZIP archive or MSI installer from the [GroupDocs Releases website](https://releases.groupdocs.com/merger/net/).

1. Download the ZIP or MSI for the desired version.
2. Extract files (ZIP) or run the installer (MSI).
3. In your project, add a reference to the `GroupDocs.Merger.dll` file for the target framework you need. The ZIP archive keeps the assemblies in the `lib` folder (for example, `lib/net8.0/GroupDocs.Merger.dll`), including the `-windows` builds; the MSI installer places them in the `bin` folder of the installation directory (`bin/net462`, `bin/net6.0`, `bin/net8.0`, `bin/net10.0`).

## Verify Installation

After installing, verify that the package is accessible by printing the loaded assembly version:

```csharp
using GroupDocs.Merger;

Console.WriteLine(typeof(Merger).Assembly.GetName().Version);
```
