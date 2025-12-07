--- 来源：https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/readableContentTypes
抓取时间：2025-12-03T05:58:29Z

---

# readableContentTypes

**Type 属性**

文档读取的文件和数据类型。

## 声明

```swift
static var readableContentTypes: [UTType] { get }
```

## 说明

定义此列表以指示文档可以读取的内容类型。默认情况下，SwiftUI 假定文档也可以写入相同的内容类型集。如果需要指定用于写入文件的不同类型集，请在此属性之外定义 [writableContentTypes](writableContentTypes.zh-Hans.md) 属性。

## 读取文档

- **init(configuration:)**：创建文档并使用文件内容对其进行初始化。

- **ReferenceFileDocument.ReadConfiguration**：读取文档内容的配置。


---
source: https://developer.apple.com/documentation/SwiftUI/ReferenceFileDocument/readableContentTypes
crawled: 2025-12-03T05:58:29Z
---

# readableContentTypes

**Type Property**

The file and data types that the document reads from.

## Declaration

```swift
static var readableContentTypes: [UTType] { get }
```

## Discussion

Define this list to indicate the content types that your document can read. By default, SwiftUI assumes that your document can also write the same set of content types. If you need to indicate a different set of types for writing files, define the [writableContentTypes](writableContentTypes.zh-Hans.md) property in addition to this property.

## Reading a document

- **init(configuration:)**: Creates a document and initializes it with the contents of a file.
- **ReferenceFileDocument.ReadConfiguration**: The configuration for reading document contents.

