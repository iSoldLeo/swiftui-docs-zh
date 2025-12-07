--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileExporter(isPresented:documents:contentType:onCompletion:)

抓取时间：2025-11-30T21:15:45Z

---

# fileExporter(isPresented:documents:contentType:onCompletion:)

**实例方法**

提供一个系统接口，用于将值类型文档集合导出到磁盘上的文件。

## 声明

```swift
nonisolated func fileExporter<C>(isPresented: Binding<Bool>, documents: C, contentType: UTType, onCompletion: @escaping (Result<[URL], any Error>) -> Void) -> some View where C : Collection, C.Element : FileDocument

```

## 参数

- **isPresented**：用于绑定是否显示此接口。

- **documents**：要导出的内存文档集合。

- **contentType**：导出文件的内容类型。

- **onCompletion**：操作成功或失败时将调用的回调函数。

## 讨论

为了使该接口显示，`isPresented` 必须等于 `true`，且 `documents` 不能为空。操作完成后，在调用 `onCompletion` 之前，`isPresented` 将被设置为 `false`。如果用户取消操作，`isPresented` 将被设置为 `false`，且不会调用 `onCompletion`。

提供的 `contentType` 必须包含在文档类型的 `writableContentTypes` 中，否则将使用第一个有效的可写内容类型。

## 导出到文件

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**：提供一个系统界面，用于将存储在值类型（例如结构体）中的文档导出到磁盘上的文件。

- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `FileDocument` 导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**：提供一个系统对话框，允许用户将符合 `FileDocument` 的文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `Transferable` 项目导出到磁盘上的文件。

- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将一组项目导出到磁盘上的文件。

- **fileExporterFilenameLabel(_:)**：在 macOS 上，为 `fileExporter` 的文件名字段配置标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileExporter(isPresented:documents:contentType:onCompletion:)
crawled: 2025-11-30T21:15:45Z
---

# fileExporter(isPresented:documents:contentType:onCompletion:)

**Instance Method**

Presents a system interface for exporting a collection of value type documents to files on disk.

## Declaration

```swift
nonisolated func fileExporter<C>(isPresented: Binding<Bool>, documents: C, contentType: UTType, onCompletion: @escaping (Result<[URL], any Error>) -> Void) -> some View where C : Collection, C.Element : FileDocument

```

## Parameters

- **isPresented**: A binding to whether the interface should be shown.
- **documents**: The collection of in-memory documents to export.
- **contentType**: The content type to use for the exported file.
- **onCompletion**: A callback that will be invoked when the operation has has succeeded or failed.

## Discussion

In order for the interface to appear, both `isPresented` must be `true` and `documents` must not be empty. When the operation is finished, `isPresented` will be set to `false` before `onCompletion` is called. If the user cancels the operation, `isPresented` will be set to `false` and `onCompletion` will not be called.

The `contentType` provided must be included within the document type’s `writableContentTypes`, otherwise the first valid writable content type will be used instead.

## Exporting to file

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**: Presents a system interface for exporting a document that’s stored in a value type, like a structure, to a file on disk.
- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface for allowing the user to export a `FileDocument` to a file on disk.
- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to export a collection of documents that conform to `FileDocument` to files on disk.
- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a `Transferable` item to file on disk.
- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a collection of items to files on disk.
- **fileExporterFilenameLabel(_:)**: On macOS, configures the `fileExporter` with a label for the file name field.

