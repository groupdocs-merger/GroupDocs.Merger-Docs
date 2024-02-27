---
id: installation
url: merger/java/installation
title: Installation
weight: 6
description: "GroupDocs.Merger for Java installation"
keywords: "groupdocs merger java, installation, maven"
productName: GroupDocs.Merger for Java
hideChildren: False
toc: True
---

## Operating Systems

**[GroupDocs.Merger for Java](https://products.groupdocs.com/merger/java)** can be executed on any Operating System with Java JDK installed.

- Windows Desktops and Servers
- Linux
- Mac OS

## Supported Runtime

**[GroupDocs.Merger for Java](https://products.groupdocs.com/merger/java)** supports Java run-time version 8 and above (Kotlin is supported as well).

## Development Environments

- NetBeans
- IntelliJ IDEA
- Eclipse

## Installation from GroupDocs Repository

All Java packages are hosted at [GroupDocs Artifact Repository](https://releases.groupdocs.com/java/repo/). You can easily reference [GroupDocs.Merger for Java API](https://releases.groupdocs.com/java/repo/com/groupdocs/groupdocs-merger/) directly in your project using following steps.

### Add GroupDocs Artifact Repository

First, you need to specify repository configuration/location in your project as follows:

{{< tabs "example1">}}
{{< tab "Maven" >}}
```xml
<repositories>
	<repository>
		<id>GroupDocs Artifact Repository</id>
        	<name>GroupDocs Artifact Repository</name>
        	<url>https://releases.groupdocs.com/java/repo/</url>
	</repository>
</repositories>
```
{{< /tab >}}
{{< tab "Gradle" >}}
```xml
repositories {
    maven {
        url "https://repository.groupdocs.com/repo/"
    }
}
```
{{< /tab >}}
{{< tab "Kotlin" >}}
```xml
repositories {
    maven(url = "https://repository.groupdocs.com/repo/")
}
```
{{< /tab >}}
{{< tab "Ivy" >}}
```xml
<ivysettings>
    <settings defaultResolver="chain"/>
    <resolvers>
        <chain name="chain">
            <ibiblio name="GroupDocs Repository" m2compatible="true" root="https://releases.groupdocs.com/java/repo/"/>
        </chain>
    </resolvers>
</ivysettings>
```
{{< /tab >}}
{{< tab "Sbt" >}}
```xml
resolvers += Resolver.url("GroupDocs Repository", url("https://releases.groupdocs.com/java/repo/"))
```
{{< /tab >}}
{{< /tabs >}}

### Add GroupDocs.Merger as a dependency

Then define GroupDocs.Merger for Java API dependency in your project as follows:

{{< tabs "example2">}}
{{< tab "Maven" >}}
```xml
<dependencies>
    <dependency>
        <groupId>com.groupdocs</groupId>
        <artifactId>groupdocs-merger</artifactId>
        <version>24.2</version>
    </dependency>
</dependencies>
```
{{< /tab >}}
{{< tab "Gradle" >}}
```xml
dependencies {
    implementation 'com.groupdocs:groupdocs-merger:24.2'
}
```
{{< /tab >}}
{{< tab "Kotlin" >}}
```xml
dependencies {
    implementation("com.groupdocs:groupdocs-merger:24.2")
}
```
{{< /tab >}}
{{< tab "Ivy" >}}
```xml
<dependency org="com.groupdocs" name="groupdocs-merger" rev="24.2">
   <artifact name="groupdocs-merger" ext="jar"/>
</dependency>
```
{{< /tab >}}
{{< tab "Sbt" >}}
```xml
libraryDependencies += "com.groupdocs" % "groupdocs-merger" % "24.2"
```
{{< /tab >}}
{{< /tabs >}}

_The latest version of Merger API can be [found here](https://releases.groupdocs.com/java/repo/com/groupdocs/groupdocs-merger/)_