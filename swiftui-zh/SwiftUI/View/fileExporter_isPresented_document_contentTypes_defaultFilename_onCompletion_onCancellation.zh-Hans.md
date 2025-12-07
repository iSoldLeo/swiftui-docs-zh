--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)

抓取时间：2025-12-02T17:30:45Z

---

# fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)

**实例方法**

提供一个系统接口，允许用户将 `FileDocument` 导出到磁盘上的文件。

## 声明

```swift
nonisolated func fileExporter<D>(isPresented: Binding<Bool>, document: D?, contentTypes: [UTType] = [], defaultFilename: String? = nil, onCompletion: @escaping (Result<URL, any Error>) -> Void, onCancellation: @escaping () -> Void = {}) -> some View where D : FileDocument

```

## 参数

- **isPresented**：绑定是否显示此接口。

- **document**：要导出的内存文档。

- **contentTypes**：可导出的支持内容类型列表。如果未提供，则使用 `FileDocument.writableContentTypes`。

- **defaultFilename**：如果提供，则为导出文件的默认名称，用户可以在导出前编辑该文件。

- **onCompletion**：操作成功或失败时将调用的回调函数。`result` 指示操作是成功还是失败。

- **onCancellation**：用户取消操作时将调用的回调函数。

## 讨论

为了显示此界面，`isPresented` 必须为 `true`。操作完成后，在调用 `onCompletion` 之前，`isPresented` 将被设置为 `false`。如果用户取消操作，`isPresented` 将被设置为 `false`，并调用 `onCancellation`。

## 导出到文件

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**：提供一个系统接口，用于将存储在值类型（例如结构体）中的文档导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentType:onCompletion:)**：提供一个系统接口，用于将值类型文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将符合 `FileDocument` 规范的文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**：显示一个系统界面，允许用户将 `Transferable` 规范的项目导出到磁盘上的文件。

- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**：显示一个系统界面，允许用户将多个项目集合导出到磁盘上的文件。

- **fileExporterFilenameLabel(_:)**：在 macOS 系统上，为 `fileExporter` 规范的文件名字段配置标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)
crawled: 2025-12-02T17:30:45Z
---

# fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)

**Instance Method**

Presents a system interface for allowing the user to export a `FileDocument` to a file on disk.

## Declaration

```swift
nonisolated func fileExporter<D>(isPresented: Binding<Bool>, document: D?, contentTypes: [UTType] = [], defaultFilename: String? = nil, onCompletion: @escaping (Result<URL, any Error>) -> Void, onCancellation: @escaping () -> Void = {}) -> some View where D : FileDocument

```

## Parameters

- **isPresented**: A binding to whether the interface should be shown.
- **document**: The in-memory document to export.
- **contentTypes**: The list of supported content types which can be exported. If not provided, `FileDocument.writableContentTypes` are used.
- **defaultFilename**: If provided, the default name to use for the exported file, which will the user will have an opportunity to edit prior to the export.
- **onCompletion**: A callback that will be invoked when the operation has succeeded or failed. The `result` indicates whether the operation succeeded or failed.
- **onCancellation**: A callback that will be invoked if the user cancels the operation.

## Discussion

In order for the interface to appear, `isPresented` must be `true`. When the operation is finished, `isPresented` will be set to `false` before `onCompletion` is called. If the user cancels the operation, `isPresented` will be set to `false` and `onCancellation` will be called.

## Exporting to file

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**: Presents a system interface for exporting a document that’s stored in a value type, like a structure, to a file on disk.
- **fileExporter(isPresented:documents:contentType:onCompletion:)**: Presents a system interface for exporting a collection of value type documents to files on disk.
- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to export a collection of documents that conform to `FileDocument` to files on disk.
- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a `Transferable` item to file on disk.
- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a collection of items to files on disk.
- **fileExporterFilenameLabel(_:)**: On macOS, configures the `fileExporter` with a label for the file name field.

