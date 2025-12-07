--- 来源：https://developer.apple.com/documentation/SwiftUI/FileDocument/ReadConfiguration
抓取时间：2025-12-03T05:58:25Z

---

# FileDocument.ReadConfiguration

**类型别名**

用于读取文档内容的配置。

## 声明

```swift
typealias ReadConfiguration = FileDocumentReadConfiguration
```

## 讨论

此类型是 [FileDocumentReadConfiguration](../FileDocumentReadConfiguration.zh-Hans.md) 的别名，它包含一个内容类型和一个文件包装器，用于访问文档文件的内容。您可以通过 [init(configuration:)](init_configuration.zh-Hans.md) 初始化器获取此类型的值作为输入。使用它可以从文件中加载文档。

## 读取文档

- **init(configuration:)**：创建一个文档并使用文件内容对其进行初始化。

- **readableContentTypes**：文档读取的文件及其数据类型。


---
source: https://developer.apple.com/documentation/SwiftUI/FileDocument/ReadConfiguration
crawled: 2025-12-03T05:58:25Z
---

# FileDocument.ReadConfiguration

**Type Alias**

The configuration for reading document contents.

## Declaration

```swift
typealias ReadConfiguration = FileDocumentReadConfiguration
```

## Discussion

This type is an alias for [FileDocumentReadConfiguration](../FileDocumentReadConfiguration.zh-Hans.md), which contains a content type and a file wrapper that you use to access the contents of a document file. You get a value of this type as an input to the [init(configuration:)](init_configuration.zh-Hans.md) initializer. Use it to load a document from a file.

## Reading a document

- **init(configuration:)**: Creates a document and initializes it with the contents of a file.
- **readableContentTypes**: The file and data types that the document reads from.

