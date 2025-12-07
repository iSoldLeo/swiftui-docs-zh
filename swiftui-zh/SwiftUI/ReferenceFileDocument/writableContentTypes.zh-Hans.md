--- 来源：https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/writableContentTypes
抓取时间：2025-12-03T05:58:33Z

---

# writableContentTypes

**Type 属性**

文档支持保存或导出的文件类型。

## 声明

```swift
static var writableContentTypes: [UTType] { get }
```

## 讨论

默认情况下，SwiftUI 假定文档读取和写入的内容类型相同。仅当需要指定不同的文件写入类型时才定义此属性。否则，此属性的默认实现将返回您在 [readableContentTypes](readableContentTypes.zh-Hans.md) 的实现中指定的列表。

## 写入文档

- **fileWrapper(snapshot:configuration:)**：将文档快照序列化为文件包装器。

- **ReferenceFileDocument.WriteConfiguration**：文档内容写入配置。


---
source: https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/writableContentTypes
crawled: 2025-12-03T05:58:33Z
---

# writableContentTypes

**Type Property**

The file types that the document supports saving or exporting to.

## Declaration

```swift
static var writableContentTypes: [UTType] { get }
```

## Discussion

By default, SwiftUI assumes that your document reads and writes the same set of content types. Only define this property if you need to indicate a different set of types for writing files. Otherwise, the default implementation of this property returns the list that you specify in your implementation of [readableContentTypes](readableContentTypes.zh-Hans.md).

## Writing a document

- **fileWrapper(snapshot:configuration:)**: Serializes a document snapshot to a file wrapper.
- **ReferenceFileDocument.WriteConfiguration**: The configuration for writing document contents.

