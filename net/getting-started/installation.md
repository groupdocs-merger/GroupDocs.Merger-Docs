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

Add directly to your `.csproj` file:

```xml
<PackageReference Include="GroupDocs.Merger" Version="26.4.0" />
```

## Runtime Packages

The NuGet package includes assemblies for four target frameworks:

| Target Framework      | Runtime Package              |
|-----------------------|------------------------------|
| .NET Framework 4.6.2  | `GroupDocs.Merger.Net462`    |
| .NET 6.0              | `GroupDocs.Merger.Net60`     |
| .NET 8.0              | `GroupDocs.Merger.Net80`     |
| .NET 10.0             | `GroupDocs.Merger.Net100`    |

In most cases, install only the main `GroupDocs.Merger` package — NuGet will resolve the correct runtime package automatically. You can also install a specific runtime package directly if needed:

```bash
dotnet add package GroupDocs.Merger.Net80
```

## Download from the Official Website

You can also download the assemblies as a ZIP archive or MSI installer from the [GroupDocs Releases website](https://releases.groupdocs.com/merger/net/).

1. Download the ZIP or MSI for the desired version.
2. Extract files (ZIP) or run the installer (MSI).
3. In your project, add a reference to the `GroupDocs.Merger.dll` file for the target framework you need (e.g., `lib/net8.0/GroupDocs.Merger.dll`).

## Verify Installation

After installing, verify that the package is accessible by printing the loaded assembly version:

```csharp
using GroupDocs.Merger;

Console.WriteLine(typeof(Merger).Assembly.GetName().Version);
```
