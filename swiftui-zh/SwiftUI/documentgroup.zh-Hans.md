--- 来源：https://developer.apple.com/documentation/swiftui/documentgroup

抓取时间：2025-12-02T17:28:57Z

---

# DocumentGroup

**Structure**

一个支持打开、创建和保存文档的场景。

## 声明

```swift
struct DocumentGroup<Document, Content> where Content : View
```

## 概述

使用 `DocumentGroup` 场景，在您使用 [App](App.zh-Hans.md) 协议声明应用时，可以告诉 SwiftUI 您的应用可以打开哪些类型的文档。

通过传入文档模型和一个能够显示该文档类型的视图来初始化文档组场景。您提供给 `DocumentGroup` 的文档类型必须符合 [FileDocument](FileDocument.zh-Hans.md) 或 [ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md) 协议。 SwiftUI 使用该模型为您的应用添加文档支持。在 macOS 中，这包括基于文档的菜单支持，以及打开多个文档的功能。在 iOS 中，这包括文档浏览器，它可以导航到文件系统中存储的文档，以及多窗口支持：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { configuration in
            ContentView(document: configuration.$document)
        }
    }
}
```

每当配置发生更改时，SwiftUI 都会使用新的配置更新内容，这与其他参数化构建器类似。

### 查看文档

如果您的应用只需要显示而不修改特定类型的文档，则可以使用文件查看器文档组场景。您需要提供文档的文件类型，以及一个显示该文档类型的视图：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(viewing: MyImageFormatDocument.self) {
            MyImageFormatViewer(image: $0.document)
        }
    }
}
```

### 支持多种文档类型

您的应用可以通过添加额外的文档组场景来支持多种文档类型：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { group in
            ContentView(document: group.$document)
        }
        DocumentGroup(viewing: MyImageFormatDocument.self) { group in
            MyImageFormatViewer(image: group.document)
        }
    }
}
```

### 访问文档 URL

如果您的应用需要知道文档的 URL，您可以从 `editor` 闭包的 `configuration` 参数中读取，该参数与文档绑定有关。创建新文档时，配置的 `fileURL` 属性为 `nil`。每次更改时，它都会传递给更新后的 `configuration` 中的 `DocumentGroup` 构建器。这样可以确保闭包中定义的视图始终知道它所托管文档的 URL。

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { configuration in
            ContentView(
                document: configuration.$document,
                fileURL: configuration.fileURL
            )
        }
    }
}
```

例如，可以使用 URL 在用户界面中显示文件名对应的文件路径。请勿使用 URL 访问文档的内容或元数据，因为这可能会与 SwiftUI 的文件管理机制冲突。请改用 [FileDocument](FileDocument.zh-Hans.md) 和 [ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md) 提供的方法来执行读写操作。

## 创建文档组

- **init(newDocument:editor:)**：创建一个用于创建和编辑文件文档的文档组。

- **init(viewing:viewer:)**：创建一个用于查看文件文档的文档组。

## 编辑由持久化存储支持的文档

- **init(editing:contentType:editor:prepareDocument:)**：实例化一个文档组，用于创建和编辑存储特定模型类型的文档。

- **init(editing:migrationPlan:editor:prepareDocument:)**：实例化一个文档组，用于创建和编辑迁移计划中最后一个 `Schema` 所描述的文档。

## 查看由持久化存储支持的文档

- **init(viewing:contentType:viewer:)**：实例化一个文档组，用于查看存储特定模型类型的文档。

- **init(viewing:migrationPlan:viewer:)**：实例化一个文档组，用于查看迁移计划中最后一个 `Schema` 所描述的文档。

## 创建文档

- **使用 SwiftUI 构建基于文档的应用**：在多平台应用中创建、保存和打开文档。

- **使用 SwiftData 构建文档型应用**：跟随 WWDC 演讲者编写代码，使用 SwiftData 改造应用。

## 符合以下规范

- 场景


---
source: https://developer.apple.com/documentation/swiftui/documentgroup
crawled: 2025-12-02T17:28:57Z
---

# DocumentGroup

**Structure**

A scene that enables support for opening, creating, and saving documents.

## Declaration

```swift
struct DocumentGroup<Document, Content> where Content : View
```

## Overview

Use a `DocumentGroup` scene to tell SwiftUI what kinds of documents your app can open when you declare your app using the [App](App.zh-Hans.md) protocol.

Initialize a document group scene by passing in the document model and a view capable of displaying the document type. The document types you supply to `DocumentGroup` must conform to [FileDocument](FileDocument.zh-Hans.md) or [ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md). SwiftUI uses the model to add document support to your app. In macOS this includes document-based menu support, including the ability to open multiple documents. On iOS this includes a document browser that can navigate to the documents stored on the file system and multiwindow support:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { configuration in
            ContentView(document: configuration.$document)
        }
    }
}
```

Any time the configuration changes, SwiftUI updates the contents with that new configuration, similar to other parameterized builders.

### Viewing documents

If your app only needs to display but not modify a specific document type, you can use the file viewer document group scene. You supply the file type of the document, and a view that displays the document type that you provide:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(viewing: MyImageFormatDocument.self) {
            MyImageFormatViewer(image: $0.document)
        }
    }
}
```

### Supporting multiple document types

Your app can support multiple document types by adding additional document group scenes:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { group in
            ContentView(document: group.$document)
        }
        DocumentGroup(viewing: MyImageFormatDocument.self) { group in
            MyImageFormatViewer(image: group.document)
        }
    }
}
```

### Accessing the document’s URL

If your app needs to know the document’s URL, you can read it from the `editor` closure’s `configuration` parameter, along with the binding to the document. When you create a new document, the configuration’s `fileURL` property is `nil`. Every time it changes, it is passed over to the `DocumentGroup` builder in the updated `configuration`. This ensures that the view you define in the closure always knows the URL of the document it hosts.

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { configuration in
            ContentView(
                document: configuration.$document,
                fileURL: configuration.fileURL
            )
        }
    }
}
```

The URL can be used, for example, to present the file path of the file name in the user interface. Don’t access the document’s contents or metadata using the URL because that can conflict with the management of the file that SwiftUI performs. Instead, use the methods that [FileDocument](FileDocument.zh-Hans.md) and [ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md) provide to perform read and write operations.

## Creating a document group

- **init(newDocument:editor:)**: Creates a document group for creating and editing file documents.
- **init(viewing:viewer:)**: Creates a document group capable of viewing file documents.

## Editing a document backed by a persistent store

- **init(editing:contentType:editor:prepareDocument:)**: Instantiates a document group for creating and editing documents that store a specific model type.
- **init(editing:migrationPlan:editor:prepareDocument:)**: Instantiates a document group for creating and editing documents described by the last `Schema` in the migration plan.

## Viewing a document backed by a persistent store

- **init(viewing:contentType:viewer:)**: Instantiates a document group for viewing documents that store a specific model type.
- **init(viewing:migrationPlan:viewer:)**: Instantiates a document group for viewing documents described by the last `Schema` in the migration plan.

## Creating a document

- **Building a document-based app with SwiftUI**: Create, save, and open documents in a multiplatform app.
- **Building a document-based app using SwiftData**: Code along with the WWDC presenter to transform an app with SwiftData.

## Conforms To

- Scene

