---
来源：https://developer.apple.com/documentation/swiftui/documentgroup/init(newdocument:editor:)-4toe2
抓取时间：2025-12-02T17:28:58Z
---

# init(newDocument:editor:)

**Initializer**

创建用于创建和编辑文件文档的文档组。

## 声明

```swift
@preconcurrency nonisolated init(newDocument: @autoclosure @escaping () -> Document, @ViewBuilder editor: @escaping (FileDocumentConfiguration<Document>) -> Content)
```

## 参数

- **newDocument**：用户创建新文档时要使用的初始文档。
- **editor**：所提供文档的编辑用户界面。

## 讨论

当您使用 [DocumentGroup](../DocumentGroup.zh-Hans.md) 协议声明您的应用程序时，请使用 [DocumentGroup](../DocumentGroup.zh-Hans.md) 场景来告诉 SwiftUI 您的应用程序可以打开哪些类型的文档。您可以通过传递文档模型和能够显示文档内容的视图来初始化文档组场景。您提供给 [DocumentGroup](../DocumentGroup.zh-Hans.md) 的文档类型必须符合 [FileDocument](../FileDocument.zh-Hans.md) 或 [ReferenceFileDocument](../ReferenceFileDocument.zh-Hans.md)。SwiftUI 使用该模型为应用程序添加文档支持。在 macOS 中，这包括基于文档的菜单支持，包括打开多个文档的功能。在 iOS 中，这包括一个文档浏览器，可以导航到存储在文件系统中的文档，并支持多窗口：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { file in
            ContentView(document: file.$document)
        }
    }
}
```

您提供给 [DocumentGroup](../DocumentGroup.zh-Hans.md) 的文档类型必须符合 [FileDocument](../FileDocument.zh-Hans.md) 或 [ReferenceFileDocument](../ReferenceFileDocument.zh-Hans.md)。您的应用程序可以通过添加额外的 [DocumentGroup](../DocumentGroup.zh-Hans.md) 场景来支持多种文档类型。


---
source: https://developer.apple.com/documentation/swiftui/documentgroup/init(newdocument:editor:)-4toe2
crawled: 2025-12-02T17:28:58Z
---

# init(newDocument:editor:)

**Initializer**

Creates a document group for creating and editing file documents.

## Declaration

```swift
@preconcurrency nonisolated init(newDocument: @autoclosure @escaping () -> Document, @ViewBuilder editor: @escaping (FileDocumentConfiguration<Document>) -> Content)
```

## Parameters

- **newDocument**: The initial document to use when a user creates a new document.
- **editor**: The editing UI for the provided document.

## Discussion

Use a [DocumentGroup](../DocumentGroup.zh-Hans.md) scene to tell SwiftUI what kinds of documents your app can open when you declare your app using the [App](../App.zh-Hans.md) protocol. You initialize a document group scene by passing in the document model and a view capable of displaying the document’s contents. The document types you supply to [DocumentGroup](../DocumentGroup.zh-Hans.md) must conform to [FileDocument](../FileDocument.zh-Hans.md) or [ReferenceFileDocument](../ReferenceFileDocument.zh-Hans.md). SwiftUI uses the model to add document support to your app. In macOS this includes document-based menu support including the ability to open multiple documents. On iOS this includes a document browser that can navigate to the documents stored on the file system and multiwindow support:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: TextFile()) { file in
            ContentView(document: file.$document)
        }
    }
}
```

The document types you supply to [DocumentGroup](../DocumentGroup.zh-Hans.md) must conform to [FileDocument](../FileDocument.zh-Hans.md) or [ReferenceFileDocument](../ReferenceFileDocument.zh-Hans.md). Your app can support multiple document types by adding additional [DocumentGroup](../DocumentGroup.zh-Hans.md) scenes.

