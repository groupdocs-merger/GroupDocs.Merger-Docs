---
id: how-to-run-examples
url: merger/net/how-to-run-examples
title: How to Run Examples
weight: 11
description: "This article describes how to run GroupDocs.Merger for .NET code examples."
keywords: GroupDocs.Merger, examples, .NET CLI, Visual Studio, C#
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: true
---
{{< alert style="warning" >}}Before running an example make sure that GroupDocs.Merger has been installed successfully.{{< /alert >}}

We offer multiple ways to run GroupDocs.Merger examples — you can build your own project from scratch, or clone our back-end examples repository and run them out of the box.

## Build a project from scratch

You can build a project from scratch using the [.NET CLI](https://docs.microsoft.com/en-us/dotnet/core/tools/) or Visual Studio. Both paths are described below.

### Build a project using .NET CLI

This method applies to .NET 6+ projects.

1. Make sure you have the [.NET SDK installed](https://dotnet.microsoft.com/download).
2. Create a directory for your console app by executing the `mkdir my-console-app` command in your terminal.
3. Navigate to the `my-console-app` directory by executing the `cd my-console-app` command.
4. Create an empty console app by executing the `dotnet new console` command.
5. Add the GroupDocs.Merger for .NET package by executing the `dotnet add package GroupDocs.Merger` command.
6. Edit `Program.cs` and add the following lines to the `Main` method:

    ```csharp
    using GroupDocs.Merger;

    // The path to the documents directory.
    string firstDocPath  = @"C:\sample.docx";  // NOTE: Put the actual path to your document here
    string secondDocPath = @"C:\sample2.docx"; // NOTE: Put the actual path to your document here
    string outputPath    = @"C:\output\result.docx";

    // Join two documents and save as result.docx.
    using (Merger merger = new Merger(firstDocPath))
    {
        merger.Join(secondDocPath);
        merger.Save(outputPath);
    }
    ```

7. Replace the `firstDocPath` and `secondDocPath` values with the actual paths to the documents you want to merge.
8. Run the project by executing the `dotnet run` command.
9. The merged document will be saved to the `C:\output\` directory.

### Build a project using Visual Studio

This method applies to both .NET 6+ and .NET Framework 4.6.2+ projects.

1. Open Visual Studio and go to **File** -> **New** -> **Project**.
2. Select the appropriate project type — Console App, ASP.NET Web Application, etc.
3. Install **GroupDocs.Merger for .NET** from NuGet. For detailed installation instructions, see the [Installation]({{< ref "merger/net/getting-started/installation.md" >}}) guide.
4. Add the following code to the `Main` method:

    ```csharp
    using GroupDocs.Merger;

    // The path to the documents directory.
    string firstDocPath  = @"C:\sample.docx";  // NOTE: Put the actual path to your document here
    string secondDocPath = @"C:\sample2.docx"; // NOTE: Put the actual path to your document here
    string outputPath    = @"C:\output\result.docx";

    // Join two documents and save as result.docx.
    using (Merger merger = new Merger(firstDocPath))
    {
        merger.Join(secondDocPath);
        merger.Save(outputPath);
    }
    ```

5. Replace the `firstDocPath` and `secondDocPath` values with the actual paths to the documents you want to merge.
6. Build and Run your project.
7. The merged document will be saved to the `C:\output\` directory.

## Run back-end examples

The complete examples package of **GroupDocs.Merger** is hosted on [GitHub](https://github.com/groupdocs-merger/GroupDocs.Merger-for-.NET). You can either download the ZIP file from [here](https://github.com/groupdocs-merger/GroupDocs.Merger-for-.NET/archive/master.zip) or clone the repository using your favorite Git client.

If you download the ZIP file, extract the folder on your local disk. The repository contains:

* `Examples/GroupDocs.Merger.Examples.CSharp.sln` — the main C# solution that bundles example projects for .NET (`GroupDocs.Merger.Examples.CSharp.Net`) and .NET Framework (`GroupDocs.Merger.Examples.CSharp.Framework`).
* `Examples/GroupDocs.Merger.Examples.CSharp/Resources/` — sample documents and images used by the examples.
* `Examples/GroupDocs.Merger.Examples.CSharp/RunExamples.cs` — the entry point that dispatches to each example method.

To run the examples:

1. Navigate to the `Examples` directory and open `GroupDocs.Merger.Examples.CSharp.sln` in your IDE (Visual Studio, JetBrains Rider, or Visual Studio Code with the C# extension).
2. Restore NuGet packages and build the solution. If references to **GroupDocs.Merger** are missing, see [Installation]({{< ref "merger/net/getting-started/installation.md" >}}).
3. Open `RunExamples.cs`, uncomment the example(s) you want to run, and comment out the rest.
4. Run the project. Output files are written to the location specified by each example.

## Contribute

If you'd like to add or improve an example, we encourage you to contribute to the project. All examples in the repository are open source and can be freely used in your own applications.

To contribute, fork the repository, edit the code, and open a pull request. We will review the changes and include them if found helpful.
