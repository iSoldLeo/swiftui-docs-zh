--- 来源：https://developer.apple.com/documentation/SwiftUI/FileDocument/init(configuration:)

抓取时间：2025-12-03T05:58:23Z

---

# init(configuration:)

**Initializer**

创建一个文档，并使用文件内容对其进行初始化。

## 声明

```swift
init(configuration: Self.ReadConfiguration) throws
```

## 参数

- **configuration**：用于读取文档数据的文件信息。

## 说明

当用户打开的文件类型与文档类型支持的类型之一匹配时，SwiftUI 会调用此初始化器。使用 `configuration` 输入的 [file](../FileDocumentReadConfiguration/file.zh-Hans.md) 属性来获取文档数据。反序列化数据，并将其存储在文档的数据结构中：

```swift
init(configuration: ReadConfiguration) throws {
    guard let data = configuration.file.regularFileContents
    else { /* Throw an error. */ }
    model = try JSONDecoder().decode(Model.self, from: data)
}
```

以上示例假设您已定义 `Model` 来存储文档数据，`Model` 符合 [doc://com.apple.documentation/documentation/Swift/Codable] 协议，并且您在文档中存储了该类型的 `model` 属性。

## 读取文档

- **readableContentTypes**：文档读取的文件及其数据类型。

- **FileDocument.ReadConfiguration**：读取文档内容的配置。


---
source: https://developer.apple.com/documentation/SwiftUI/FileDocument/init(configuration:)
crawled: 2025-12-03T05:58:23Z
---

# init(configuration:)

**Initializer**

Creates a document and initializes it with the contents of a file.

## Declaration

```swift
init(configuration: Self.ReadConfiguration) throws
```

## Parameters

- **configuration**: Information about the file that you read document data from.

## Discussion

SwiftUI calls this initializer when someone opens a file type that matches one of those that your document type supports. Use the [file](../FileDocumentReadConfiguration/file.zh-Hans.md) property of the `configuration` input to get document’s data. Deserialize the data, and store it in your document’s data structure:

```swift
init(configuration: ReadConfiguration) throws {
    guard let data = configuration.file.regularFileContents
    else { /* Throw an error. */ }
    model = try JSONDecoder().decode(Model.self, from: data)
}
```

The above example assumes that you define `Model` to contain the document’s data, that `Model` conforms to the [doc://com.apple.documentation/documentation/Swift/Codable] protocol, and that you store a `model` property of that type inside your document.



## Reading a document

- **readableContentTypes**: The file and data types that the document reads from.
- **FileDocument.ReadConfiguration**: The configuration for reading document contents.

