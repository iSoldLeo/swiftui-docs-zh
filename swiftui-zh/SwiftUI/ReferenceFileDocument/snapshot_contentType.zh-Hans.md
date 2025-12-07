--- 来源：https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/snapshot(contentType:)

抓取时间：2025-12-01T10:47:27Z

---

# snapshot(contentType:)

**实例方法**

创建一个快照，用于表示文档的当前状态。

## 声明

```swift
func snapshot(contentType: UTType) throws -> Self.Snapshot
```

## 参数

- **contentType**：要为其创建文档快照的内容类型。

## 返回值

系统提供给 [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) 方法进行序列化的文档内容快照。

## 说明

要存储文档（例如，响应保存命令），SwiftUI 首先会调用此方法。返回您实现的文档内容副本。例如，您可以为文档的模型对象定义一个初始化器，该初始化器会复制文档实例的内容并返回该内容：

```swift
func snapshot(contentType: UTType) throws -> Snapshot {
    Model(from: model) // Creates a copy.
}
```

SwiftUI 会在快照操作期间阻止文档编辑，以确保模型状态保持一致。调用完成后，SwiftUI 会重新启用编辑功能，然后调用 [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) 方法，在该方法中，您可以将快照序列化并存储到文件中。

## 获取快照

- **Snapshot**：表示文档已存储内容的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/snapshot(contentType:)
crawled: 2025-12-01T10:47:27Z
---

# snapshot(contentType:)

**Instance Method**

Creates a snapshot that represents the current state of the document.

## Declaration

```swift
func snapshot(contentType: UTType) throws -> Self.Snapshot
```

## Parameters

- **contentType**: The content type that you create the document snapshot for.

## Return Value

A snapshot of the document content that the system provides to the [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) method for serialization.

## Discussion

To store a document — for example, in response to a Save command — SwiftUI begins by calling this method. Return a copy of the document’s content from your implementation of the method. For example, you might define an initializer for your document’s model object that copies the contents of the document’s instance, and return that:

```swift
func snapshot(contentType: UTType) throws -> Snapshot {
    Model(from: model) // Creates a copy.
}
```

SwiftUI prevents document edits during the snapshot operation to ensure that the model state remains coherent. After the call completes, SwiftUI reenables edits, and then calls the [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) method, where you serialize the snapshot and store it to a file.



## Getting a snapshot

- **Snapshot**: A type that represents the document’s stored content.

