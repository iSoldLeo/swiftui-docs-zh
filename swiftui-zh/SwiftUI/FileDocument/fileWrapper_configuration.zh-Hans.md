--- 来源：https://developer.apple.com/documentation/swiftui/filedocument/filewrapper(configuration:)

抓取时间：2025-12-02T17:29:07Z

---

# fileWrapper(configuration:)

**实例方法**

将文档快照序列化为文件包装器。

## 声明

```swift
func fileWrapper(configuration: Self.WriteConfiguration) throws -> FileWrapper
```

## 参数

- **configuration**：文档已存在文件的信息（如有）。

## 返回值

要将文档内容序列化到的目标位置。该值可以是新创建的 [doc://com.apple.documentation/documentation/Foundation/FileWrapper]，也可以是 `configuration` 输入中提供的文件的更新值。

## 说明

要存储文档（例如，响应保存命令），SwiftUI 会调用此方法。使用此方法序列化文档数据，并创建或修改包含序列化数据的文件包装器：

```swift
func fileWrapper(configuration: WriteConfiguration) throws -> FileWrapper {
    let data = try JSONEncoder().encode(model)
    return FileWrapper(regularFileWithContents: data)
}
```

## 写入文档

- **writableContentTypes**：文档支持保存或导出的文件类型。

- **FileDocument.WriteConfiguration**：文档内容写入配置。


---
source: https://developer.apple.com/documentation/swiftui/filedocument/filewrapper(configuration:)
crawled: 2025-12-02T17:29:07Z
---

# fileWrapper(configuration:)

**Instance Method**

Serializes a document snapshot to a file wrapper.

## Declaration

```swift
func fileWrapper(configuration: Self.WriteConfiguration) throws -> FileWrapper
```

## Parameters

- **configuration**: Information about a file that already exists for the document, if any.

## Return Value

The destination to serialize the document contents to. The value can be a newly created [doc://com.apple.documentation/documentation/Foundation/FileWrapper] or an update of the one provided in the `configuration` input.

## Discussion

To store a document — for example, in response to a Save command — SwiftUI calls this method. Use it to serialize the document’s data and create or modify a file wrapper with the serialized data:

```swift
func fileWrapper(configuration: WriteConfiguration) throws -> FileWrapper {
    let data = try JSONEncoder().encode(model)
    return FileWrapper(regularFileWithContents: data)
}
```



## Writing a document

- **writableContentTypes**: The file types that the document supports saving or exporting to.
- **FileDocument.WriteConfiguration**: The configuration for writing document contents.

