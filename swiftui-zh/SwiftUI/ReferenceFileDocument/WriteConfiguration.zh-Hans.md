--- 来源：https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/WriteConfiguration
抓取时间：2025-12-03T05:58:34Z

---

# ReferenceFileDocument.WriteConfiguration

**类型别名**

用于写入文档内容的配置。

## 声明

```swift
typealias WriteConfiguration = FileDocumentWriteConfiguration
```

## 讨论

此类型是 [FileDocumentWriteConfiguration](../FileDocumentWriteConfiguration.zh-Hans.md) 的别名，它包含一个内容类型和一个文件包装器，用于访问文档文件的内容（如果文档文件已存在）。您可以通过 [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) 方法获取此类型的值作为输入。

## 写入文档

- **fileWrapper(snapshot:configuration:)**：将文档快照序列化为文件包装器。

- **writableContentTypes**：文档支持保存或导出的文件类型。


---
source: https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/WriteConfiguration
crawled: 2025-12-03T05:58:34Z
---

# ReferenceFileDocument.WriteConfiguration

**Type Alias**

The configuration for writing document contents.

## Declaration

```swift
typealias WriteConfiguration = FileDocumentWriteConfiguration
```

## Discussion

This type is an alias for [FileDocumentWriteConfiguration](../FileDocumentWriteConfiguration.zh-Hans.md), which contains a content type and a file wrapper that you use to access the contents of a document file, if one already exists. You get a value of this type as an input to the [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) method.

## Writing a document

- **fileWrapper(snapshot:configuration:)**: Serializes a document snapshot to a file wrapper.
- **writableContentTypes**: The file types that the document supports saving or exporting to.

