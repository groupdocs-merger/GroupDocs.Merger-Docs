---
id: password-merge
url: groupdocs.merger/java/password-merge
title: Password Merge for PDFs
description: Automate unlocking, merging, and re‑protecting password‑protected PDFs with GroupDocs.Merger for Java.
keywords:
  - GroupDocs.Merger
  - password merge
  - PDF merge
  - Java
  - document security
  - batch processing
productName: GroupDocs.Merger for Java
toc: true
hideChildren: false
draft: true
---

# Password Merge Use Case

Password merge is a GroupDocs.Merger capability for Java that unlocks multiple password‑protected PDFs, merges them into a single document, and applies a unified credential. This workflow eliminates manual decryption steps and ensures the final archive complies with corporate security policies.

{{< alert style="info" >}}
💡 Full working example available on GitHub: [repository](https://github.com/groupdocs-merger/merge-protected-pdfs-with-passwords-using-groupdocs-merger-java)
{{< /alert >}}

## Overview

Enterprises often receive batches of PDFs where each file is secured with a different password—think legal contracts, financial statements, or audit reports. Consolidating these documents into a searchable binder is essential for efficient review, but differing passwords block straightforward merging. By programmatically detecting protection, unlocking each file with its specific credential, and re‑securing the combined output with a single password, developers can automate this tedious process. The steps demonstrated below run in under two minutes on a typical developer laptop and require only the GroupDocs.Merger Java library (v24.6 released in 2024)【https://releases.groupdocs.com/merger/java/release-notes/latest/】.

I needed this solution when my team had to bundle five investor contracts, each encrypted by a different reviewer, into a single archive for board approval.

## Prerequisites

- Java Development Kit (JDK) 11 or newer.
- Maven 3.6+ for building the project.
- GroupDocs.Merger for Java 24.6 (or later) – obtain a temporary license for development from the [GroupDocs portal](https://purchase.groupdocs.com/temp-license/100464).
- A collection of PDF files, each optionally paired with its password.

## Installation

Add the GroupDocs.Merger dependency to your `pom.xml`:
```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-merger</artifactId>
    <version>24.6</version>
</dependency>
```
Then run:
```bash
mvn clean compile
```
This will download the library and compile the demo sources.

## Repository Structure

```
password-merge-demo/
│   pom.xml
│
├── documents/
│   ├── public.pdf               # No password
│   ├── secret1.pdf              # Owner password: "alpha"
│   └── secret2.pdf              # Owner password: "beta"
│
└── src/main/java/com/groupdocs/demo/
    └── PasswordMergeDemo.java   # Core implementation
```
- **pom.xml** – Maven project definition.
- **documents/** – Sample PDFs used in the demo.
- **PasswordMergeDemo.java** – Contains all four helper methods referenced in the usage steps.

## Usage Example

The workflow consists of four logical steps. Each step is illustrated with a dedicated code block extracted directly from the sample project.

### Step 1: Detect Protection

Before attempting decryption, verify whether a PDF is password‑protected. This avoids unnecessary `LoadOptions` creation.
```java
public boolean isDocumentProtected(String path, String password) {
    Merger merger;
    if (password == null || password.isEmpty()) {
        merger = new Merger(path);
    } else {
        merger = new Merger(path, new LoadOptions(password));
    }
    try {
        return merger.isPasswordSet(); // true for owner or user passwords
    } finally {
        merger.dispose(); // releases native resources
    }
}
```
*Key point:* `isPasswordSet()` is documented in the official API reference【https://reference.groupdocs.com/merger/java/】.

### Step 2: Unlock All PDFs

Iterate over a map of file paths to passwords. Files without a password are read directly; protected files are opened with `LoadOptions`, stripped of protection via `removePassword()`, and stored as byte arrays.
```java
public List<byte[]> unlockAll(Map<String, String> sources) throws IOException {
    List<byte[]> unlocked = new ArrayList<>();
    for (Map.Entry<String, String> e : sources.entrySet()) {
        String path = e.getKey();
        String pwd = e.getValue();
        System.out.println("Unlocking (credentials=" + (pwd != null ? "yes" : "no") + "): " + path);
        if (pwd == null || pwd.isEmpty()) {
            unlocked.add(Files.readAllBytes(Paths.get(path)));
        } else {
            LoadOptions opts = new LoadOptions(pwd);
            ByteArrayOutputStream buf = new ByteArrayOutputStream();
            Merger m = new Merger(path, opts);
            try {
                m.removePassword();
                m.save(buf);
            } finally {
                m.dispose();
            }
            unlocked.add(buf.toByteArray());
        }
    }
    return unlocked;
}
```
*Key point:* `removePassword()` permanently clears encryption; the resulting bytes are safe to merge.

### Step 3: Merge and Apply a Unified Password

Create a `Merger` from the first unlocked stream, join the remaining streams, then protect the combined document with `AddPasswordOptions`.
```java
public void mergeAndProtect(List<byte[]> unlockedPdfs,
                            String unifiedPassword,
                            String outputPath) {
    InputStream first = new ByteArrayInputStream(unlockedPdfs.get(0));
    Merger merger = new Merger(first);
    try {
        for (int i = 1; i < unlockedPdfs.size(); i++) {
            merger.join(new ByteArrayInputStream(unlockedPdfs.get(i)));
        }
        merger.addPassword(new AddPasswordOptions(unifiedPassword));
        merger.save(outputPath);
    } finally {
        merger.dispose();
    }
    System.out.println("Merged output: " + new File(outputPath).getAbsolutePath());
    System.out.println("Unified password: " + unifiedPassword);
}
```
*Key point:* The final PDF is written once, minimizing I/O overhead.

### Step 4 (Optional): Rotate the Unified Password

If security policies require periodic password changes, update the credential without re‑merging.
```java
public void rotateUnifiedPassword(String path,
                                 String oldPassword,
                                 String newPassword,
                                 String outputPath) {
    Merger merger = new Merger(path, new LoadOptions(oldPassword));
    try {
        merger.updatePassword(new UpdatePasswordOptions(newPassword));
        merger.save(outputPath);
    } finally {
        merger.dispose();
    }
    System.out.println("Rotated output: " + new File(outputPath).getAbsolutePath());
    System.out.println("New password: " + newPassword);
}
```
*Key point:* `updatePassword` rewrites the encryption header only, making the operation fast even for large PDFs.

## When to Use This Approach

Choose this pipeline when you need to process a batch of PDFs that each may have a distinct password, and the final deliverable must be a single, uniformly protected file. It is ideal for compliance‑driven environments (e.g., GDPR, HIPAA) where audit trails require a single password for archived documents. If all source PDFs share the same password, a simpler single‑call `addPassword` after merge may suffice, but the presented method scales gracefully to heterogeneous credential sets.

## Common Pitfalls

1. **Forgetting to dispose `Merger` instances** – native resources remain allocated, leading to `OutOfMemoryError` in long‑running services. Always wrap usage in a `try/finally` block as shown.
2. **Reading large PDFs into memory** – the `unlockAll` method stores each file as a byte array; for files >100 MB, consider streaming to temporary files instead of keeping them in a list.
3. **Mismatched passwords** – supplying an incorrect password to `LoadOptions` throws a `PasswordException`. Validate credentials early with `isDocumentProtected` to surface issues before the unlock loop.

## Notes

- The API supports additional formats (DOCX, XLSX, PPTX). Replace `Merger` constructors with appropriate streams to handle mixed‑type batches.
- The temporary license used for development expires after 30 days; obtain a production license before deployment.
- All examples target Java 11; earlier JDK versions may require additional module configuration.

## FAQ

**Q: Can I merge PDFs that have both owner and user passwords?**
A: Yes. The `isPasswordSet` method detects any encryption, and `removePassword` works regardless of whether the password is an owner or user credential. Just provide the correct password in `LoadOptions`.

**Q: What happens if a PDF is corrupted?**
A: The `Merger` constructor will throw an `IOException`. It is advisable to catch the exception, log the file name, and continue processing the remaining documents.

**Q: Is it possible to preserve original metadata (author, creation date) after merging?**
A: After merging, you can call `merger.updateMetadata(...)` before saving. This feature is documented in the API reference【https://reference.groupdocs.com/merger/java/}**.

**Q: How large a batch can this approach handle?**
A: The memory footprint is roughly the sum of all unlocked PDFs. For batches exceeding 500 MB, switch to a streaming approach: write each unlocked PDF to a temporary file and join using file paths instead of in‑memory byte arrays.

**Q: Do I need to re‑apply digital signatures after merging?**
A: Merging invalidates existing signatures. Use GroupDocs.Signature to re‑sign the final document if compliance requires it.

## Conclusion

By leveraging GroupDocs.Merger for Java, developers can automate the end‑to‑end process of detecting, unlocking, merging, and re‑securing password‑protected PDFs. The four‑step workflow scales from a handful of contracts to thousands of files, reduces manual effort, and ensures the final archive complies with security policies. Integrate the provided code snippets into your CI pipeline to achieve fully automated PDF bundling.

## See Also

- [GroupDocs.Merger Java Documentation](https://docs.groupdocs.com/merger/java/)
- [API Reference for Java](https://reference.groupdocs.com/merger/java/)
- [Release Notes (v24.6, 2024)](https://releases.groupdocs.com/merger/java/release-notes/latest/)
- [Community Forum](https://forum.groupdocs.com/c/merger/)