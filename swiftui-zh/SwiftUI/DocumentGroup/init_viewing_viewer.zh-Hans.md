---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(viewing:viewer:)
抓取时间： 2025-12-01T00:42:52Z
---

# init(viewing:viewer:)

**Initializer**

创建可查看文件文档的文档组。

## 声明

```swift
nonisolated init(viewing documentType: Document.Type, @ViewBuilder viewer: @escaping (FileDocumentConfiguration<Document>) -> Content)
```

## 参数

- **documentType**：应用程序可以查看的文档类型。
- **viewer**：所提供文档的查看用户界面。

## 讨论

使用此方法可创建可查看特定类型文件的文档组。下面的示例为 `MyImageFormatDocument` 创建了一个新的文档查看器，并用 `MyImageFormatViewer` 显示它们：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(viewing: MyImageFormatDocument.self) { file in
            MyImageFormatViewer(image: file.document)
        }
    }
}
```

您可以通过设置[doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/CFBundleDocumentTypes/CFBundleTypeRole] `Info.plist` 键的值为`Viewer`，告诉系统应用程序在文档类型方面的角色。

## 创建文件组

- **init(newDocument:editor:)**：创建用于创建和编辑文件文档的文档组。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(viewing:viewer:)
crawled: 2025-12-01T00:42:52Z
---

# init(viewing:viewer:)

**Initializer**

Creates a document group capable of viewing file documents.

## Declaration

```swift
nonisolated init(viewing documentType: Document.Type, @ViewBuilder viewer: @escaping (FileDocumentConfiguration<Document>) -> Content)
```

## Parameters

- **documentType**: The type of document your app can view.
- **viewer**: The viewing UI for the provided document.

## Discussion

Use this method to create a document group that can view files of a specific type. The example below creates a new document viewer for `MyImageFormatDocument` and displays them with `MyImageFormatViewer`:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(viewing: MyImageFormatDocument.self) { file in
            MyImageFormatViewer(image: file.document)
        }
    }
}
```

You tell the system about the app’s role with respect to the document type by setting the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/CFBundleDocumentTypes/CFBundleTypeRole] `Info.plist` key with a value of `Viewer`.

## Creating a document group

- **init(newDocument:editor:)**: Creates a document group for creating and editing file documents.

