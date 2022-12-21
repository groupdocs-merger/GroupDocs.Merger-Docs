---
id: licensing-and-subscription
url: merger/net/licensing-and-subscription
title: Licensing and  Subscription
weight: 6
description: "This article explains evaluation limitations and licensing of GroupDocs.Merger for .NET. Please note that you can avail a Free Trial and a 30-day Temporary License for evaluation"
keywords: Free Trial, Temporary License for evaluation
productName: GroupDocs.Merger for .NET
hideChildren: False
toc: true
---

Sometimes, in order to study the system better, you want to dive into the code as fast as possible. To make this easier, GroupDocs.Merger provides different plans for purchase or offers a Free Trial and a 30-day Temporary License for evaluation.

{{< alert style="info" >}}
Note that there are a number of general policies and practices that guide you on how to evaluate, properly license, and purchase our products. You can find them in the ["Purchase Policies and FAQ"](https://purchase.groupdocs.com/policies) section.
{{< /alert >}}

## Free Trial or Temporary License

You can try GroupDocs.Merger without buying a license.

### Free Trial

The evaluation version is the same as the purchased one – the evaluation version simply becomes licensed when you set the license. You can set the license in a number of ways that described in the next sections of this article.

The evaluation version comes with the limitations:

- Resultant document will be trimmed to first 3 pages.
- Trial badges are placed in the document on the top of each page.

### Temporary License

If you wish to test GroupDocs.Merger without the limitations of the trial version, you can also request a 30-day Temporary License. For more details, see the ["Get a Temporary License"](https://purchase.groupdocs.com/temporary-license) page.

## How to set a license

The license file contains details such as the product name, number of developers it is licensed to, subscription expiry date and so on. It contains the digital signature, so don't modify the file. Even inadvertent addition of an extra line break into the file will invalidate it. You need to set a license before utilizing GroupDocs.Merger API if you want to avoid its evaluation limitations.
The license can be loaded from a file or stream object. The easiest way to set a license is to put the license file in the same folder as the GroupDocs.Merger.dll file and specify the file name, without a path, as shown in the examples below.

### Setting License from File

The code below will explain how to set product license.

```csharp
// For complete examples and data files, please go to https://github.com/groupdocs-merger/GroupDocs.Merger-for-.NET
// Setup license.
License license = new License();
license.SetLicense(licensePath);
```

### Setting License from Stream

The following example shows how to load a license from a stream.

```csharp
// For complete examples and data files, please go to https://github.com/groupdocs-merger/GroupDocs.Merger-for-.NET
using (FileStream fileStream = File.OpenRead("GroupDocs.Merger.lic"))
{
    License license = new License();
    license.SetLicense(fileStream);
}
```

{{< alert style="info" >}}Calling [License](https://reference.groupdocs.com/merger/net/groupdocs.merger/license).[SetLicense](https://reference.groupdocs.com/merger/net/groupdocs.merger/license/setlicense) multiple times is not harmful but simply wastes processor time. If you are developing a Windows Forms or console application, call License.SetLicense in your startup code, before using GroupDocs.Merger classes.  
When developing an ASP.NET application, you can call License.SetLicense from the Global.asax.cs (Global.asax.vb) file in the Application\_Start protected method. It is called once when the application starts.  
Do not call [License](https://reference.groupdocs.com/merger/net/groupdocs.merger/license).[SetLicense](https://reference.groupdocs.com/merger/net/groupdocs.merger/license/setlicense) from within Page\_Load methods since it means the license will be loaded every time a web page is loaded.
{{< /alert >}}

### Setting Metered License

{{< alert style="info" >}}You can also set [Metered](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered) license as an alternative to license file. It is a new licensing mechanism that will be used along with existing licensing method. It is useful for the customers who want to be billed based on the usage of the API features. For more details, please refer to [Metered Licensing FAQ](https://purchase.groupdocs.com/faqs/licensing/metered) section.{{< /alert >}}
Here are the simple steps to use the `Metered` class.

1. Create an instance of [Metered](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered) class.
2. Pass public & private keys to [SetMeteredKey](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered/setmeteredkey) method.
3. Do processing (perform task).
4. call method [GetConsumptionQuantity](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered/getconsumptionquantity) of the `Metered` class.
5. It will return the amount/quantity of API requests that you have consumed so far.
6. call method [GetConsumptionCredit](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered/getconsumptioncredit) of the [Metered](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered) class.
7. It will return the credit that you have consumed so far.

Following is the sample code demonstrating how to use [Metered](https://reference.groupdocs.com/merger/net/groupdocs.merger/metered) class.

```csharp
// For complete examples and data files, please go to https://github.com/groupdocs-merger/GroupDocs.Merger-for-.NET
string publicKey = ""; // Your public license key
string privateKey = ""; // Your private license key

Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);

// Get amount (MB) consumed
decimal amountConsumed = GroupDocs.Merger.Metered.GetConsumptionQuantity();
Console.WriteLine("Amount (MB) consumed: " + amountConsumed);

// Get count of credits consumed
decimal creditsConsumed = GroupDocs.Merger.Metered.GetConsumptionCredit();
Console.WriteLine("Credits consumed: " + creditsConsumed);
```
