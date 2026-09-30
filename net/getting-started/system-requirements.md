---
id: system-requirements
url: merger/net/system-requirements
title: System requirements
weight: 7
description: GroupDocs.Merger for .NET can be used on any operating system where the .NET framework is installed
keywords: GroupDocs.Merger for .NET, Merger
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: True
---
{{< alert style="info" >}}

GroupDocs.Merger for .NET does not require any external software or third-party tools to be installed. To install GroupDocs.Merger for .NET just follow one of the ways as described in the [Installation]({{< ref "merger/net/getting-started/installation.md" >}}) section. On Linux and macOS, processing OneNote and SVG documents needs the additional dependencies described in [Linux and macOS](#linux-and-macos-additional-dependencies).

{{< /alert >}}

## Supported Operating Systems


GroupDocs.Merger for .NET can be used on any operating system where the .NET framework is installed including, but not limited to:

### Windows

*   Microsoft Windows Server 2012 R2 and later
*   Microsoft Windows 7 SP1 and later (x64, x86)
*   Microsoft Windows 10 (x64, x86, Arm64)
*   Microsoft Windows 11 (x64, Arm64)

On Windows Arm64, target `net6.0-windows`, `net8.0-windows` or `net10.0-windows` so that the Windows runtime package is used (see [Installation]({{< ref "merger/net/getting-started/installation.md" >}})).

### Linux

*   Ubuntu 18.04 and later
*   Debian 10 and later
*   CentOS 7 and later
*   Fedora 33 and later
*   Alpine 3.13 and later

### macOS

*   macOS 10.15 (Catalina) and later (x64, Arm64)

## Linux and macOS: additional dependencies

The cross-platform runtime packages (`GroupDocs.Merger.Net60`, `GroupDocs.Merger.Net80` and `GroupDocs.Merger.Net100`) do not depend on `System.Drawing.Common`. Most document formats do not need it, but processing **OneNote** and **SVG** documents does. To process these formats on Linux or macOS:

*   Add the `System.Drawing.Common` package, version 6.0.0, to your application.
*   Install `libgdiplus` on the machine.
*   Enable the `System.Drawing.EnableUnixSupport` runtime switch, for example in your project file:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Drawing.EnableUnixSupport" Value="true" />
</ItemGroup>
```

If a required component is missing, the operation throws `MissingDependencyException` (in the `GroupDocs.Merger.Exceptions` namespace). Its message names the missing component and how to install it.

## Supported Frameworks

GroupDocs.Merger for .NET supports .NET frameworks as follows:

*   .NET Framework 4.6.2 and later
*   .NET 6.0 and later


## Development Environments

GroupDocs.Merger for .NET can be used to develop applications in any development environment that targets the .NET platform, but the following environments are explicitly supported:

*   Microsoft Visual Studio 2017 and later
*   JetBrains Rider
*   Visual Studio Code with C# extension
