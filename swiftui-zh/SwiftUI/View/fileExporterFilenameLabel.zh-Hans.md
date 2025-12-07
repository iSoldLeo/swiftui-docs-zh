--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileExporterFilenameLabel(_:)

抓取时间：2025-11-30T21:15:49Z

---

# fileExporterFilenameLabel(_:)

**实例方法**

在 macOS 上，为文件名字段配置标签 `fileExporter`。

## 声明

```swift
nonisolated func fileExporterFilenameLabel(_ label: LocalizedStringResource) -> some View

```

## 参数

- **label**：要显示的本地化字符串资源。

## 导出到文件

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**：提供一个系统接口，用于将存储在值类型（例如结构体）中的文档导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentType:onCompletion:)**：提供一个系统界面，用于将值类型文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `FileDocument` 导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**：提供一个系统对话框，允许用户将符合 `FileDocument` 的文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `Transferable` 项目导出到磁盘上的文件。

- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将项目集合导出到磁盘上的文件。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileExporterFilenameLabel(_:)
crawled: 2025-11-30T21:15:49Z
---

# fileExporterFilenameLabel(_:)

**Instance Method**

On macOS, configures the `fileExporter` with a label for the file name field.

## Declaration

```swift
nonisolated func fileExporterFilenameLabel(_ label: LocalizedStringResource) -> some View

```

## Parameters

- **label**: The localized string resource to display.

## Exporting to file

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**: Presents a system interface for exporting a document that’s stored in a value type, like a structure, to a file on disk.
- **fileExporter(isPresented:documents:contentType:onCompletion:)**: Presents a system interface for exporting a collection of value type documents to files on disk.
- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface for allowing the user to export a `FileDocument` to a file on disk.
- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to export a collection of documents that conform to `FileDocument` to files on disk.
- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a `Transferable` item to file on disk.
- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a collection of items to files on disk.

