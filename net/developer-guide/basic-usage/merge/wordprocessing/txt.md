---
id: merge-txt
url: merger/net/merge/txt
title: Merge TXT
description: "Learn how to merge TXT files, combine TXT files into one file programmatically in C# language using GroupDocs.Merger for .NET library."
keywords: Merge TXT files in C#, Combine TXT files programmatically
productName: GroupDocs.Merger for .NET

---

## How to merge TXT files in C#

[GroupDocs.Merger](https://products.groupdocs.com/merger/net) allows developers to merge TXT files when it's needed to organize multiple
 TXT files into single document or send fewer attachments etc. And you can do this without any third-party software or manual work involved.
 With GroupDocs.Merger it is possible to combine TXT documents of any size and structure - all text, images, tables, graphs, forms and other content will be preserved.

The following example demonstrates how to merge TXT files with several lines of code:

* Create an instance of [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements.
* Add another TXT file to merge with [Join](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/join/index) method. Repeat this step for other TXT documents you want to merge.
* Call [Merger](https://apireference.groupdocs.com/net/merger/groupdocs.merger/merger) class [Save](https://apireference.groupdocs.com/merger/net/groupdocs.merger/merger/methods/save/index) method and specify the filename for the merged TXT file as parameter.

```csharp
// Load the source TXT file
using (Merger merger = new Merger(@"c:\sample1.txt"))
{
    // Add another TXT file to merge
    merger.Join(@"c:\sample2.txt");
    // Merge TXT files ans save result
    merger.Save(@"c:\merged.txt");
}
```

### About TXT File Format 

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "merger/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Merge TXT Live Demo 

GroupDocs.Merger for .NET provides an online [**TXT Merger App**](https://products.groupdocs.app/merger/txt), which allows you to try it for free and check its quality and accuracy.

[!["Merge TXT"](merger/net/images/merge-txt.png)](https://products.groupdocs.app/merger/txt)