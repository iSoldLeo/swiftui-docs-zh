---

来源：https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/Snapshot
抓取时间：2025-12-03T05:58:32Z

---

# 快照

**关联类型**

表示文档存储内容的类型。

## 声明

```swift
associatedtype Snapshot
```

## 说明

定义此类型以表示文档存储的所有数据。当用户发出保存命令时，SwiftUI 会调用文档的 [snapshot(contentType:)](snapshot_contentType.zh-Hans.md) 方法，请求此类型的值。SwiftUI 会将您提供的快照发送到文档的 [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) 方法，您需要在该方法中将快照的内容序列化为文件包装器。

## 获取快照

- **snapshot(contentType:)**：创建代表文档当前状态的快照。


---
source: https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/Snapshot
crawled: 2025-12-03T05:58:32Z
---

# Snapshot

**Associated Type**

A type that represents the document’s stored content.

## Declaration

```swift
associatedtype Snapshot
```

## Discussion

Define this type to represent all the data that your document stores. When someone issues a Save command, SwiftUI asks your document for a value of this type by calling the document’s [snapshot(contentType:)](snapshot_contentType.zh-Hans.md) method. SwiftUI sends the snapshot that you provide to the document’s [fileWrapper(snapshot:configuration:)](fileWrapper_snapshot_configuration.zh-Hans.md) method, where you serialize the contents of the snapshot into a file wrapper.

## Getting a snapshot

- **snapshot(contentType:)**: Creates a snapshot that represents the current state of the document.

