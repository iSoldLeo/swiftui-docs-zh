---
来源： https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument
抓取时间： 2025-12-02T17:29:12Z
---

# 参考文件

**Protocol**

用于将引用类型文档序列化到文件或从文件中序列化的类型。

### 声明

```swift
@preconcurrency protocol ReferenceFileDocument : ObservableObject, Sendable
```

## 概览

要将文档作为引用类型（如类）存储，请创建一个符合`ReferenceFileDocument` 协议的类型，并实现所需的方法和属性。您的实现：

- 通过定义[readableContentTypes](ReferenceFileDocument/readableContentTypes.zh-Hans.md)，提供文档可读取和写入的内容类型列表。如果文档可写入的内容类型列表与文档可读取的内容类型不同，则还可选择定义 [writableContentTypes](ReferenceFileDocument/writableContentTypes.zh-Hans.md)。
- 在 [init(configuration:)](ReferenceFileDocument/init_configuration.zh-Hans.md) 初始化程序中从文件加载文档。
- 在 [snapshot(contentType:)](ReferenceFileDocument/snapshot_contentType.zh-Hans.md) 方法中提供文档内容的快照，然后在 [fileWrapper(snapshot:configuration:)](ReferenceFileDocument/fileWrapper_snapshot_configuration.zh-Hans.md) 方法中序列化该内容，从而将文档存储到文件中。

确保符合此协议的类型是 `Sendable`。特别是，SwiftUI 会从不同的隔离域调用协议方法。不要在`MainActor`上执行序列化和反序列化。

```swift
final class PDFDocument: ReferenceFileDocument {
    struct Storage {
        var contents: Data
    }

    static let readableContentTypes: [UTType] = [.pdf]
    let storage: Mutex<Storage>

    required init(configuration: ReadConfiguration) throws {
       guard let data = configuration.file.regularFileContents else {
           throw CocoaError(.fileReadCorruptFile)
       }
        self.storage = .init(.init(contents: data))
    }

    func snapshot(contentType: UTType) throws -> Data {
        storage.withLock { $0.contents }
    }

    func fileWrapper(snapshot: Data, configuration: WriteConfiguration) throws -> FileWrapper {
        return FileWrapper(regularFileWithContents: snapshot)
    }
}
```



## 阅读文件

- **init(configuration:)**：创建文档并用文件内容对其进行初始化。
- **readableContentTypes**：文档读取的文件和数据类型。
- **ReferenceFileDocument.ReadConfiguration**：读取文件内容的配置。

## 获取快照

- **snapshot(contentType:)**：创建代表文档当前状态的快照。
- **Snapshot**：表示文档存储内容的类型。

## 写入文档

- **fileWrapper(snapshot:configuration:)**：将文档快照序列化为文件封装器。
- **writableContentTypes**：文档支持保存或导出的文件类型。
- **ReferenceFileDocument.WriteConfiguration**：用于写入文档内容的配置。

## 在类实例中存储文档数据

- **ReferenceFileDocumentConfiguration**：打开的引用文件文档的属性。
- **undoManager**：用于注册视图撤销操作的撤销管理器。

## 继承自

- 可观察对象
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument
crawled: 2025-12-02T17:29:12Z
---

# ReferenceFileDocument

**Protocol**

A type that you use to serialize reference type documents to and from file.

## Declaration

```swift
@preconcurrency protocol ReferenceFileDocument : ObservableObject, Sendable
```

## Overview

To store a document as a reference type — like a class — create a type that conforms to the `ReferenceFileDocument` protocol and implement the required methods and properties. Your implementation:

- Provides a list of the content types that the document can read from and write to by defining [readableContentTypes](ReferenceFileDocument/readableContentTypes.zh-Hans.md). If the list of content types that the document can write to is different from those that it reads from, you can optionally also define [writableContentTypes](ReferenceFileDocument/writableContentTypes.zh-Hans.md).
- Loads documents from file in the [init(configuration:)](ReferenceFileDocument/init_configuration.zh-Hans.md) initializer.
- Stores documents to file by providing a snapshot of the document’s content in the [snapshot(contentType:)](ReferenceFileDocument/snapshot_contentType.zh-Hans.md) method, and then serializing that content in the [fileWrapper(snapshot:configuration:)](ReferenceFileDocument/fileWrapper_snapshot_configuration.zh-Hans.md) method.

Ensure that types that conform to this protocol are `Sendable`. In particular, SwiftUI calls the protocol’s methods from different isolation domains. Don’t perform serialization and deserialization on `MainActor`.

```swift
final class PDFDocument: ReferenceFileDocument {
    struct Storage {
        var contents: Data
    }

    static let readableContentTypes: [UTType] = [.pdf]
    let storage: Mutex<Storage>

    required init(configuration: ReadConfiguration) throws {
       guard let data = configuration.file.regularFileContents else {
           throw CocoaError(.fileReadCorruptFile)
       }
        self.storage = .init(.init(contents: data))
    }

    func snapshot(contentType: UTType) throws -> Data {
        storage.withLock { $0.contents }
    }

    func fileWrapper(snapshot: Data, configuration: WriteConfiguration) throws -> FileWrapper {
        return FileWrapper(regularFileWithContents: snapshot)
    }
}
```



## Reading a document

- **init(configuration:)**: Creates a document and initializes it with the contents of a file.
- **readableContentTypes**: The file and data types that the document reads from.
- **ReferenceFileDocument.ReadConfiguration**: The configuration for reading document contents.

## Getting a snapshot

- **snapshot(contentType:)**: Creates a snapshot that represents the current state of the document.
- **Snapshot**: A type that represents the document’s stored content.

## Writing a document

- **fileWrapper(snapshot:configuration:)**: Serializes a document snapshot to a file wrapper.
- **writableContentTypes**: The file types that the document supports saving or exporting to.
- **ReferenceFileDocument.WriteConfiguration**: The configuration for writing document contents.

## Storing document data in a class instance

- **ReferenceFileDocumentConfiguration**: The properties of an open reference file document.
- **undoManager**: The undo manager used to register a view’s undo operations.

## Inherits From

- ObservableObject
- Sendable
- SendableMetatype

