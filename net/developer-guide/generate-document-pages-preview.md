---
id: generate-document-pages-preview
url: merger/net/generate-document-pages-preview
title: Generate document pages preview
weight: 7
description: "Following this guide you will learn how to generate PDF, Word (DOC, DOCX), Excel(XLS, XLSX), PowerPoint(PPT, PPTX) documents thumbnails and preview document pages using GroupDocs.Merger for .NET API."
keywords: Preview document pages, Document pages as PNG, document pages as JPG, Document preview
productName: GroupDocs.Merger for .NET
hideChildren: False
---
**[GroupDocs.Merger](https://products.groupdocs.com/merger/net)** provides [PreviewOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/previewoptions) class to specify different options to manage preview of document pages.  
  
Here are the steps to generate document preview with GroupDocs.Merger:
*   Create new instance of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class and pass source document path as a constructor parameter.    
*   Instantiate the [PreviewOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/previewoptions) object with:    
    *   delegate for each page stream creation (see event handler [CreatePageStream](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.common/createpagestream));         
    *   image preview format - PNG / JPG / BMP;        
    *   page numbers to process;        
    *   custom size of preview images (if needed).           
{{< alert style="info" >}} 
Stream that were created by [CreatePageStream](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.common/createpagestream) delegate will be disposed automatically once after generation of preview image. If you need to implement custom image preview stream disposing you have to pass additional argument [ReleasePageStream](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.common/releasepagestream) to clean up resources.  
{{< /alert >}}     
*   Call [GeneratePreview](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger/generatepreview) method of [Merger](https://reference.groupdocs.com/merger/net/groupdocs.merger/merger) class instance and pass [PreviewOptions](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.options/previewoptions) to it.
    

## CreatePageStream delegate implementation

GroupDocs.Merger expects [CreatePageStream](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.common/createpagestream) delegate to obtain each page stream for image preview generation process

```csharp
private static Stream CreatePageStream(int pageNumber)
{
    string imageFilePath = Path.Combine("GeneratePreviewFolder", "image-" + pageNumber.ToString() + ".jpg");
    var folder = Path.GetDirectoryName(imageFilePath);
    if(!Directory.Exists(folder))
    {
        Directory.CreateDirectory(folder);
    }
    return new System.IO.FileStream(imageFilePath, FileMode.Create);
}
```

## ReleasePageStream delegate implementation

```csharp
private static void ReleasePageStream(int pageNumber, Stream pageStream)
{
     pageStream.Dispose();
     string imageFilePath = Path.Combine("GeneratePreviewFolder", "image-" + pageNumber.ToString() + ".jpg");
     Console.WriteLine("Image file {0} is ready for preview", imageFilePath);
}
```

## Generate document preview from file on local disk

```csharp
public static void GetPreview()
{   
    string filePath = @"c:\sample.xlsx";
    using (Merger merger = new Merger(filePath))
    {
        IPreviewOptions previewOption = new PreviewOptions(CreatePageStream, PreviewMode.JPEG);
        merger.GeneratePreview(previewOption);
    }
}
 
private static Stream CreatePageStream(int pageNumber)
{
    string imageFilePath = Path.Combine("GeneratePreviewFolder", "image-" + pageNumber.ToString() + ".jpg");
    var folder = Path.GetDirectoryName(imageFilePath);
    if(!Directory.Exists(folder))
    {
        Directory.CreateDirectory(folder);
    }
    return new System.IO.FileStream(imageFilePath, FileMode.Create);
}
```

## Generate document preview from stream with custom stream releasing delegate

```csharp
public static void GetPreview()
{
    string filePath = @"c:\sample.xlsx";
    using (Merger merger = new Merger(filePath))
    {
        IPreviewOptions previewOption = new PreviewOptions(CreatePageStream, ReleasePageStream, PreviewMode.JPEG);
        merger.GeneratePreview(previewOption);
    }
}
 
private static Stream CreatePageStream(int pageNumber)
{
    string imageFilePath = Path.Combine("GeneratePreviewFolder", "image-" + pageNumber.ToString() + ".jpg");
    var folder = Path.GetDirectoryName(imageFilePath);
    if(!Directory.Exists(folder))
    {
        Directory.CreateDirectory(folder);
    }
    return new System.IO.FileStream(imageFilePath, FileMode.Create);
}

private static void ReleasePageStream(int pageNumber, Stream pageStream)
{
     pageStream.Dispose();
     string imageFilePath = Path.Combine("GeneratePreviewFolder", "image-" + pageNumber.ToString() + ".jpg");
     Console.WriteLine("Image file {0} is ready for preview", imageFilePath);
}
```

{{< alert style="info" >}}
NOTE: Stream that was created over [CreatePageStream](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.common/createpagestream) delegate will be disposed automatically once after generation of preview image. If you need to implement custom image preview stream disposing you have to pass additional argument [ReleasePageStream](https://reference.groupdocs.com/merger/net/groupdocs.merger.domain.common/releasepagestream) to clean up resources.
{{< /alert >}}

