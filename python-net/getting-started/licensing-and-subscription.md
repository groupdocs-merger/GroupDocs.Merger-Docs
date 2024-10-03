---
id: licensing-and-evaluation
url: merger/python-net/licensing-and-evaluation
title: Licensing and evaluation
weight: 5
keywords: free, free trial, evaluation, groupdocs merger net
description: "GroupDocs.Merger for Python provides different plans for purchase or offers a Free Trial and a 30-day Temporary License for evaluation."
productName: GroupDocs.Merger for Python via .NET
hideChildren: False
toc: True
aliases:
    - /merger/python-net/licensing-and-subscription/
---

To study the system, you may want quick access to the API. To make this easier, GroupDocs.Merger provides different plans for purchase and offers a Free Trial and a 30-day Temporary License for evaluation.

{{< alert style="info" >}}

Note that there are a number of general policies and practices that guide you on how to evaluate, properly license, and purchase our products. You can find them in the [Purchase Policies and FAQ](https://purchase.groupdocs.com/policies) section.

{{< /alert >}}

## Purchased License

After buying, apply the license file or include it as an embedded resource. 

License needs to be set:
- Only once per application domain
- Before using any other GroupDocs.Merger classes
    
### License Applying Options

Licenses can be applied from different locations:

*   Explicit path
*   The folder containing the _GroupDocs.Merger.dll_ file
*   The folder containing the assembly that called _GroupDocs.Merger.dll_
*   The folder containing the entry assembly (your _.exe_)
*   As a Metered License that allows you to pay for your usage. For details, see the [Metered Licensing FAQ](https://purchase.groupdocs.com/faqs/licensing/metered/).

When you reference _GroupDocs.Merger.dll_ in the application, the library is copied to your output directory (unless **Copy Local** in the properties for that entry is set to false). The easiest way to set a license is often to place the license file in the same folder as _GroupDocs.Merger.dll_ and specify just the filename without the path.

Use the [setLicense](https://reference.groupdocs.com/merger/net/groupdocs.merger/license/setlicense/) method to license a component.

Calling `setLicense` multiple times is not harmful, it simply wastes processor time.

Calling [setMeteredKey](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered/setmeteredkey/) multiple times is not harmful either but wastes processor time and can accumulate consumption improperly.

#### Apply the License

After obtaining the license, set it. This section explains how to do this. When developing your application, call the `setLicense` method in your startup code before using the GroupDocs.Merger classes.

##### Set a License from a File

The following code snippet shows how to set a license from file:

{{< tabs "example1">}}
{{< tab "JavaScript" >}}

```python
license_path = "path to the .lic file"
license = gm.License()
license.set_license(license_path)
```

{{< /tab >}}
{{< /tabs >}}

##### Set a License from a Stream

The following code snippet shows how to set a license from a stream:

{{< tabs "example2">}}
{{< tab "JavaScript" >}}

```python
license_path = "path to the .lic file"
with open(license_path, "rb") as stream:
    gm.License().set_license(stream)
```

{{< /tab >}}
{{< /tabs >}}

### Changing the License File Name

You do not have to name the license file "GroupDocs.Merger.lic". Feel free to rename it as you prefer, and use that name when setting the license in your application.

### "Cannot find license filename" Exception

When you buy and download a license from the GroupDocs website, the license file is named "GroupDocs.Merger.lic." Download it using your browser. Sometimes, browsers recognize it as XML and add the .xml extension, making the full file name "GroupDocs.Merger.lic.XML" on your computer.

If Microsoft Windows is set to hide file extensions (which is the default in most installations), the license file will show as "GroupDocs.Merger.lic" in Windows Explorer. You might assume this is the actual file name and call the `setLicense` method with "GroupDocs.Merger.lic", but there is no such file, leading to an exception.

To fix this issue, rename the file to remove the hidden .xml extension. Additionally, we suggest disabling the "Hide extensions" option in Microsoft Windows.

## How to Evaluate GroupDocs.Merger

You can also try GroupDocs.Merger without buying a license.

### Free Trial

The evaluation version is identical to the purchased one; it becomes licensed once you set the license. You can set the license using methods described in the following sections of this article.

The evaluation version has the following limitations:

- Rendering is limited to the first 2 pages.
- Trial badges are added to the top of a rendered page.

### Temporary License

If you want to test GroupDocs.Merger without the limitations of the trial version,   request a 30-day Temporary License. For details, see the ["Get a Temporary License"](https://purchase.groupdocs.com/temporary-license) page.