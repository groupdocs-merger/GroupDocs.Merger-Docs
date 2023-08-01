---
id: licensing-and-subscription
url: merger/java/licensing-and-subscription
title: Licensing and Subscription
weight: 7
description: "This article explains evaluation limitations and licensing of GroupDocs.Merger for Java"
keywords: 
productName: GroupDocs.Merger for Java
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

```java
// For complete examples and data files, please go to https://github.com/groupdocs-merger/GroupDocs.Merger-for-Java
// Setup license.
License license = new License();
license.setLicense(licensePath);
```

### Setting License from Stream

The following example shows how to load a license from a stream.

```java
// For complete examples and data files, please go to https://github.com/groupdocs-merger/GroupDocs.Merger-for-Java
InputStream fileStream = new FileInputStream("GroupDocs.Merger.lic"))
License license = new License();
license.setLicense(fileStream);
```

{{< alert style="info" >}}Calling License.setLicense multiple times is not harmful but simply wastes processor time. Call License.setLicense in your startup code, before using GroupDocs.Merger classes. Do not call License.setLicense from within Page_Load methods since it means the license will be loaded every time a web page is loaded.{{< /alert >}}

### Setting Metered License

{{< alert style="info" >}}You can also set [Metered](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered) license as an alternative to license file. It is a new licensing mechanism that will be used along with existing licensing method. It is useful for the customers who want to be billed based on the usage of the API features. For more details, please refer to [Metered Licensing FAQ](https://purchase.groupdocs.com/faqs/licensing/metered) section.{{< /alert >}}
Here are the simple steps to use the [Metered](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered) class.

1. Create an instance of [Metered](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered) class.
2. Pass public & private keys to [setMeteredKey](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered#setMeteredKey(java.lang.String,%20java.lang.String)) method.
3. Do processing (perform task).
4. call method [getConsumptionQuantity](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered#getConsumptionQuantity()) of the [Metered](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered) class.
5. It will return the amount/quantity of API requests that you have consumed so far.
6. call method [getConsumptionCredit](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered#getConsumptionCredit()) of the [Metered](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered) class.
7. It will return the credit that you have consumed so far.

Following is the sample code demonstrating how to use [Metered](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered) class.

Following is the sample code demonstrating how to use [Metered](https://reference.groupdocs.com/merger/java/com.groupdocs.merger.licensing.metered/Metered) class.

```java
// For complete examples and data files, please go to https://github.com/groupdocs-merger/GroupDocs.Merger-for-Java
string publicKey = ""; // Your public license key
string privateKey = ""; // Your private license key

Metered metered = new Metered();
metered.setMeteredKey(publicKey, privateKey);

// Get amount (MB) consumed
double amountConsumed = Metered.getConsumptionQuantity();
System.out.print("Amount (MB) consumed: " + amountConsumed);

// Get count of credits consumed
double creditsConsumed = Metered.getConsumptionCredit();
System.out.print("Credits consumed: " + creditsConsumed);
```