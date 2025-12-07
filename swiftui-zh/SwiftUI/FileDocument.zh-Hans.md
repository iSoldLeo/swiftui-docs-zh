--- 来源：https://developer.apple.com/documentation/SwiftUI/FileDocument
抓取时间：2025-12-02T17:29:11Z

---

# FileDocument

**Protocol**

用于将文档序列化为文件和从文件序列化文档的类型。

## 声明

```swift
@preconcurrency protocol FileDocument : Sendable
```

## 概述

要将文档存储为值类型（例如结构体），请创建一个符合 `FileDocument` 协议的类型，并实现所需的方法和属性。您的实现：

- 通过定义 [readableContentTypes](FileDocument/readableContentTypes.zh-Hans.md) 提供文档可以读取和写入的内容类型列表。如果文档可以写入的内容类型列表与可以读取的内容类型列表不同，您还可以选择定义 [writableContentTypes](FileDocument/writableContentTypes.zh-Hans.md)。

- 在 [init(configuration:)](FileDocument/init_configuration.zh-Hans.md) 初始化器中从文件中加载文档。

- 在 [fileWrapper(configuration:)](FileDocument/fileWrapper_configuration.zh-Hans.md) 方法中通过序列化文档内容将其存储到文件中。

确保符合此协议的类型为 `Sendable`。尤其需要注意的是，SwiftUI 会从不同的隔离域调用协议的方法。请勿对 `MainActor` 执行序列化和反序列化。

## 读取文档

- **init(configuration:)**：创建文档并使用文件内容对其进行初始化。

- **readableContentTypes**：文档读取的文件及其数据类型。

- **FileDocument.ReadConfiguration**：读取文档内容的配置。

## 写入文档

- **fileWrapper(configuration:)**：将文档快照序列化为文件包装器。

- **writableContentTypes**：文档支持保存或导出的文件类型。

- **FileDocument.WriteConfiguration**：写入文档内容的配置。

## 将文档数据存储在结构实例中

- **FileDocumentConfiguration**：已打开文件文档的属性。

## 继承自

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/FileDocument
crawled: 2025-12-02T17:29:11Z
---

# FileDocument

**Protocol**

A type that you use to serialize documents to and from file.

## Declaration

```swift
@preconcurrency protocol FileDocument : Sendable
```

## Overview

To store a document as a value type — like a structure — create a type that conforms to the `FileDocument` protocol and implement the required methods and properties. Your implementation:

- Provides a list of the content types that the document can read from and write to by defining [readableContentTypes](FileDocument/readableContentTypes.zh-Hans.md). If the list of content types that the document can write to is different from those that it reads from, you can optionally also define [writableContentTypes](FileDocument/writableContentTypes.zh-Hans.md).
- Loads documents from file in the [init(configuration:)](FileDocument/init_configuration.zh-Hans.md) initializer.
- Stores documents to file by serializing their content in the [fileWrapper(configuration:)](FileDocument/fileWrapper_configuration.zh-Hans.md) method.



Ensure that types that conform to this protocol are `Sendable`. In particular, SwiftUI calls the protocol’s methods from different isolation domains. Don’t perform serialization and deserialization on `MainActor`.

## Reading a document

- **init(configuration:)**: Creates a document and initializes it with the contents of a file.
- **readableContentTypes**: The file and data types that the document reads from.
- **FileDocument.ReadConfiguration**: The configuration for reading document contents.

## Writing a document

- **fileWrapper(configuration:)**: Serializes a document snapshot to a file wrapper.
- **writableContentTypes**: The file types that the document supports saving or exporting to.
- **FileDocument.WriteConfiguration**: The configuration for writing document contents.

## Storing document data in a structure instance

- **FileDocumentConfiguration**: The properties of an open file document.

## Inherits From

- Sendable
- SendableMetatype

