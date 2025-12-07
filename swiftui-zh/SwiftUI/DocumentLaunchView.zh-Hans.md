--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView
抓取时间：2025-12-02T17:26:58Z

---

# DocumentLaunchView

**Structure**

用于在启动与文档相关的用户体验时显示的视图。

## 声明

```swift
struct DocumentLaunchView<Actions, DocumentView> where Actions : View, DocumentView : View
```

## 概述

配置 `DocumentLaunchView` 以打开和显示文件并触发自定义操作。

例如，提供写作功能的应用程序可以将 `DocumentLaunchView` 显示为其启动视图：

```swift
public import UniformTypeIdentifiers

struct BookEditorLaunchView: View {

    var body: some View {
        DocumentLaunchView(for: [.book]) {
            NewDocumentButton("Start New Book")
        } onDocumentOpen: { url in
            BookEditor(url)
        }
    }
}

struct BookEditor: View {
    init(_ url: URL) { }
}

extension UTType {
    static let book = UTType(exportedAs: "com.example.bookEditor")
}
```

## 初始化器

- **init(_:for:_:onDocumentOpen:)**：创建一个视图，用于在启动与文档相关的用户体验时显示，并带有本地化标题和自定义操作。

- **init(_:for:_:onDocumentOpen:background:)**：创建一个视图，用于在使用本地化标题、自定义操作和背景视图启动与文档相关的用户体验时显示。

- **init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作、背景视图和背景辅助视图启动与文档相关的用户体验时显示。

- **init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:overlayAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作、背景视图和辅助视图启动与文档相关的用户体验时显示。

- **init(_:for:_:onDocumentOpen:background:overlayAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作、背景视图和叠加辅助视图启动与文档相关的用户体验时显示。

- **init(_:for:_:onDocumentOpen:backgroundAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作和背景辅助视图启动与文档相关的用户体验时显示。

- **init(_:for:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作和辅助视图启动文档相关用户体验时显示。

- **init(_:for:_:onDocumentOpen:overlayAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作和叠加辅助视图启动文档相关用户体验时显示。

- **init(_:for:backgroundStyle:_:onDocumentOpen:)**：创建一个视图，用于在使用本地化标题、自定义操作和背景样式启动文档相关用户体验时显示。

- **init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作、背景样式和背景辅助视图启动文档相关用户体验时显示。

- **init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)**：创建一个视图，用于在使用本地化标题、自定义操作、背景样式和辅助视图启动文档相关用户体验时显示。

- **init(_:for:backgroundStyle:_:onDocumentOpen:overlayAccessoryView:)**：创建一个视图，用于在启动与文档相关的用户体验时显示，该视图包含本地化标题、自定义操作、背景样式和叠加辅助视图。

## 实例属性

- **body**：视图主体。

## 配置文档启动体验

- **DocumentGroupLaunchScene**：基于文档的应用程序的启动场景。

- **DocumentLaunchGeometryProxy**：用于访问场景框架及其标题视图的代理。

- **DefaultDocumentGroupLaunchActions**：文档组启动场景和文档启动视图的默认操作。

- **NewDocumentButton**：用于创建和打开新文档的按钮。

- **DocumentBaseBox**：一种允许设置文档底座的盒子，无需调用者了解盒子及其底座的具体类型。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView
crawled: 2025-12-02T17:26:58Z
---

# DocumentLaunchView

**Structure**

A view to present when launching document-related user experience.

## Declaration

```swift
struct DocumentLaunchView<Actions, DocumentView> where Actions : View, DocumentView : View
```

## Overview



Configure `DocumentLaunchView` to open and display files and trigger custom actions.

For example, an application that offers writing books can present the `DocumentLaunchView` as its launch view:

```swift
public import UniformTypeIdentifiers

struct BookEditorLaunchView: View {

    var body: some View {
        DocumentLaunchView(for: [.book]) {
            NewDocumentButton("Start New Book")
        } onDocumentOpen: { url in
            BookEditor(url)
        }
    }
}

struct BookEditor: View {
    init(_ url: URL) { }
}

extension UTType {
    static let book = UTType(exportedAs: "com.example.bookEditor")
}
```

## Initializers

- **init(_:for:_:onDocumentOpen:)**: Creates a view to present when launching document-related user experiences using a localized title and custom actions.
- **init(_:for:_:onDocumentOpen:background:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, and a background view.
- **init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background view, and a background accessory view.
- **init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:overlayAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background view, and accessory views.
- **init(_:for:_:onDocumentOpen:background:overlayAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background view, and an overlay accessory view.
- **init(_:for:_:onDocumentOpen:backgroundAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, and a background accessory view.
- **init(_:for:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, and accessory views.
- **init(_:for:_:onDocumentOpen:overlayAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, and an overlay accessory view.
- **init(_:for:backgroundStyle:_:onDocumentOpen:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, and a background style.
- **init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background style, and a background accessory view.
- **init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background style, and accessory views.
- **init(_:for:backgroundStyle:_:onDocumentOpen:overlayAccessoryView:)**: Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background style, and an overlay accessory view.

## Instance Properties

- **body**: The body of the view.

## Configuring the document launch experience

- **DocumentGroupLaunchScene**: A launch scene for document-based applications.
- **DocumentLaunchGeometryProxy**: A proxy for access to the frame of the scene and its title view.
- **DefaultDocumentGroupLaunchActions**: The default actions for the document group launch scene and the document launch view.
- **NewDocumentButton**: A button that creates and opens new documents.
- **DocumentBaseBox**: A Box that allows setting its Document base not requiring the caller to know the exact types of the box and its base.

## Conforms To

- View

