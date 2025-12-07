--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)

抓取时间：2025-11-30T21:15:48Z

---

# fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)

**实例方法**

提供一个系统界面，允许用户将 `Transferable` 项导出到磁盘上的文件。

## 声明

```swift
nonisolated func fileExporter<T>(isPresented: Binding<Bool>, item: T?, contentTypes: [UTType] = [], defaultFilename: String? = nil, onCompletion: @escaping (Result<URL, any Error>) -> Void, onCancellation: @escaping () -> Void = { }) -> some View where T : Transferable

```

## 参数

- **isPresented**：绑定是否显示此界面。

- **item**：要保存到磁盘的项。

- **contentTypes**：导出文件要使用的可选内容类型。如果为空，SwiftUI 将使用 `transferRepresentation` 属性中为 `Transferable` 一致性提供的内容类型。

- **onCompletion**：操作成功或失败时将调用的回调函数。

- **onCancellation**：操作取消时将调用的回调函数。

## 讨论

为了使界面显示，`isPresented` 必须设置为 `true`。操作完成后，在调用 `onCompletion` 之前，`isPresented` 将被设置为 `false`。如果用户取消操作，`isPresented` 将被设置为 `false`，并且不会调用 `onCompletion`。

## 导出到文件

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**：提供一个系统接口，用于将存储在值类型（例如结构体）中的文档导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentType:onCompletion:)**：提供一个系统接口，用于将值类型文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统接口，允许用户将 `FileDocument` 导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将符合 `FileDocument` 标准的文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**：显示一个系统界面，允许用户将项目集合导出到磁盘上的文件。

- **fileExporterFilenameLabel(_:)**：在 macOS 上，为 `fileExporter` 的文件名字段配置标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)
crawled: 2025-11-30T21:15:48Z
---

# fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)

**Instance Method**

Presents a system interface allowing the user to export a `Transferable` item to file on disk.

## Declaration

```swift
nonisolated func fileExporter<T>(isPresented: Binding<Bool>, item: T?, contentTypes: [UTType] = [], defaultFilename: String? = nil, onCompletion: @escaping (Result<URL, any Error>) -> Void, onCancellation: @escaping () -> Void = { }) -> some View where T : Transferable

```

## Parameters

- **isPresented**: A binding to whether the interface should be shown.
- **item**: The item to be saved on disk.
- **contentTypes**: The optional content types to use for the exported file. If empty, SwiftUI uses the content types from the `transferRepresentation` property provided for `Transferable` conformance.
- **onCompletion**: A callback that will be invoked when the operation has succeeded or failed.
- **onCancellation**: A callback that will be invoked if the operation was cancelled.

## Discussion

In order for the interface to appear `isPresented` must be set to `true`. When the operation is finished, `isPresented` will be set to `false` before `onCompletion` is called. If the user cancels the operation, `isPresented` will be set to `false` and `onCompletion` will not be called.

## Exporting to file

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**: Presents a system interface for exporting a document that’s stored in a value type, like a structure, to a file on disk.
- **fileExporter(isPresented:documents:contentType:onCompletion:)**: Presents a system interface for exporting a collection of value type documents to files on disk.
- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface for allowing the user to export a `FileDocument` to a file on disk.
- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to export a collection of documents that conform to `FileDocument` to files on disk.
- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a collection of items to files on disk.
- **fileExporterFilenameLabel(_:)**: On macOS, configures the `fileExporter` with a label for the file name field.

