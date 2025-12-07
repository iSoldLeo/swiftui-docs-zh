--- 来源：https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/fileWrapper(snapshot:configuration:)

抓取时间：2025-12-03T05:58:32Z

---

# fileWrapper(snapshot:configuration:)

**实例方法**

将文档快照序列化为文件包装器。

## 声明

```swift
func fileWrapper(snapshot: Self.Snapshot, configuration: Self.WriteConfiguration) throws -> FileWrapper
```

## 参数

- **snapshot**：要保存的文档快照。

- **configuration**：如果存在与该文档对应的文件，则返回该文件的相关信息。

## 返回值

要将文档内容序列化到的目标位置。该值可以是新创建的 [doc://com.apple.documentation/documentation/Foundation/FileWrapper]，也可以是对 `configuration` 输入中提供的值的更新。

## 讨论

要存储文档（例如，响应保存命令），SwiftUI 首先调用 [snapshot(contentType:)](snapshot_contentType.zh-Hans.md) 方法获取当前状态的文档数据副本。然后，SwiftUI 将该快照传递给此方法，在此方法中，您可以序列化该快照并使用序列化数据创建或修改文件包装器：

```swift
func fileWrapper(snapshot: Snapshot, configuration: WriteConfiguration) throws -> FileWrapper {
    let data = try JSONEncoder().encode(snapshot)
    return FileWrapper(regularFileWithContents: data)
}
```

SwiftUI 在快照期间禁用文档编辑，以确保文档数据保持一致，但在序列化操作期间重新启用编辑。

## 写入文档

- **writableContentTypes**：文档支持保存或导出的文件类型。

- **ReferenceFileDocument.WriteConfiguration**：写入文档内容的配置。


---
source: https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/fileWrapper(snapshot:configuration:)
crawled: 2025-12-03T05:58:32Z
---

# fileWrapper(snapshot:configuration:)

**Instance Method**

Serializes a document snapshot to a file wrapper.

## Declaration

```swift
func fileWrapper(snapshot: Self.Snapshot, configuration: Self.WriteConfiguration) throws -> FileWrapper
```

## Parameters

- **snapshot**: The document snapshot to save.
- **configuration**: Information about a file that already exists for the document, if any.

## Return Value

The destination to serialize the document contents to. The value can be a newly created [doc://com.apple.documentation/documentation/Foundation/FileWrapper] or an update of the one provided in the `configuration` input.

## Discussion

To store a document — for example, in response to a Save command — SwiftUI begins by calling the [snapshot(contentType:)](snapshot_contentType.zh-Hans.md) method to get a copy of the document data in its current state. Then SwiftUI passes that snapshot to this method, where you serialize it and create or modify a file wrapper with the serialized data:

```swift
func fileWrapper(snapshot: Snapshot, configuration: WriteConfiguration) throws -> FileWrapper {
    let data = try JSONEncoder().encode(snapshot)
    return FileWrapper(regularFileWithContents: data)
}
```

SwiftUI disables document edits during the snapshot to ensure that the document’s data remains coherent, but reenables edits during the serialization operation.



## Writing a document

- **writableContentTypes**: The file types that the document supports saving or exporting to.
- **ReferenceFileDocument.WriteConfiguration**: The configuration for writing document contents.

