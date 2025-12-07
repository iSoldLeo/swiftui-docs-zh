--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene
抓取时间：2025-12-02T17:29:25Z

---

# DocumentGroupLaunchScene

**Structure**

用于基于文档的应用程序的启动场景。

## 声明

```swift
struct DocumentGroupLaunchScene<Actions> where Actions : View
```

## 概述

您可以将此启动场景与 [DocumentGroup](DocumentGroup.zh-Hans.md) 场景一起使用。如果您未在应用程序声明中实现 `DocumentGroup`，则可以通过实现 [DocumentLaunchView](DocumentLaunchView.zh-Hans.md) 来获得相同的设计。

如果您未提供场景标题，则会显示应用程序名称。如果您未提供操作构建器，则场景将使用默认的“创建文档”操作来创建新文档。要自定义文档启动体验，您可以替换标准屏幕背景和标题，添加装饰性视图以及自定义操作。

`DocumentGroupLaunchScene` 配置底部面板上的文档浏览器，使其打开应用程序定义中所有文档组的内容类型。`DocumentGroupLaunchScene` 还配置文档组，使其创建应用程序可以创建和写入的第一个内容类型的文档。

更多信息，请参阅 `FileDocument.writableContentTypes` 和 `ReferenceFileDocument.writableContentTypes`。

## 初始化程序

- **init(_:_:background:)**：为基于文档的应用程序创建启动场景，包含标题、一组操作和背景。

- **init(_:_:background:backgroundAccessoryView:)**：为基于文档的应用程序创建启动场景，包含标题、一组操作、背景和背景辅助视图。

- **init(_:_:background:backgroundAccessoryView:overlayAccessoryView:)**：为基于文档的应用程序创建启动场景，包含标题、一组操作和背景。

- **init(_:_:background:overlayAccessoryView:)**：为基于文档的应用程序创建启动场景，包含标题、一组操作、背景和叠加辅助视图。

- **init(_:backgroundStyle:_:)**：为基于文档的应用程序创建启动场景，包含标题、背景样式和一组操作。

- **init(_:backgroundStyle:_:backgroundAccessoryView:)**：为基于文档的应用程序创建启动场景，包含标题、背景样式、一组操作和背景辅助视图。

- **init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)**：为基于文档的应用程序创建启动场景，包含标题、背景样式、一组操作以及背景和叠加辅助视图。

- **init(_:backgroundStyle:_:overlayAccessoryView:)**：为基于文档的应用程序创建启动场景，包含标题、背景样式、一组操作和一个叠加辅助视图。

## 配置文档启动体验

- **DocumentLaunchView**：启动文档相关用户体验时显示的视图。

- **DocumentLaunchGeometryProxy**：用于访问场景框架及其标题视图的代理。

- **DefaultDocumentGroupLaunchActions**：文档组启动场景和文档启动视图的默认操作。

- **NewDocumentButton**：用于创建和打开新文档的按钮。

- **DocumentBaseBox**：一个允许设置其文档基准的框，无需调用者了解框及其基准的确切类型。

## 符合以下规范

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroupLaunchScene
crawled: 2025-12-02T17:29:25Z
---

# DocumentGroupLaunchScene

**Structure**

A launch scene for document-based applications.

## Declaration

```swift
struct DocumentGroupLaunchScene<Actions> where Actions : View
```

## Overview

You can use this launch scene alongside [DocumentGroup](DocumentGroup.zh-Hans.md) scenes. If you don’t implement a `DocumentGroup` in the app declaration, you can get the same design by implementing a [DocumentLaunchView](DocumentLaunchView.zh-Hans.md).

If you don’t provide the title of the scene, it displays the application name. If you don’t provide the actions builder, the scene has the default “Create Document” action that creates new documents. To customize the document launch experience, you can replace the standard screen background and title, add decorative views, and add custom actions.

A `DocumentGroupLaunchScene` configures the document browser on the bottom sheet to open content types from all the document groups in the app definition. A `DocumentGroupLaunchScene` also configures the document groups to create documents of the first content type that your application can create and write.

For more information, see `FileDocument.writableContentTypes` and `ReferenceFileDocument.writableContentTypes`.

## Initializers

- **init(_:_:background:)**: Creates a launch scene for document-based applications with a title, a set of actions, and a background.
- **init(_:_:background:backgroundAccessoryView:)**: Creates a launch scene for document-based applications with a title, a set of actions, a background, and a background accessory view.
- **init(_:_:background:backgroundAccessoryView:overlayAccessoryView:)**: Creates a launch scene for document-based applications with a title, a set of actions, and a background.
- **init(_:_:background:overlayAccessoryView:)**: Creates a launch scene for document-based applications with a title, a set of actions, a background, and an overlay accessory view.
- **init(_:backgroundStyle:_:)**: Creates a launch scene for document-based applications with a title, a background style, and a set of actions.
- **init(_:backgroundStyle:_:backgroundAccessoryView:)**: Creates a launch scene for document-based applications with a title, a background style, a set of actions, and a background accessory view.
- **init(_:backgroundStyle:_:backgroundAccessoryView:overlayAccessoryView:)**: Creates a launch scene for document-based applications with a title, a background style, a set of actions, and background and overlay accessory views.
- **init(_:backgroundStyle:_:overlayAccessoryView:)**: Creates a launch scene for document-based applications with a title, a background style, a set of actions, and an overlay accessory view.

## Configuring the document launch experience

- **DocumentLaunchView**: A view to present when launching document-related user experience.
- **DocumentLaunchGeometryProxy**: A proxy for access to the frame of the scene and its title view.
- **DefaultDocumentGroupLaunchActions**: The default actions for the document group launch scene and the document launch view.
- **NewDocumentButton**: A button that creates and opens new documents.
- **DocumentBaseBox**: A Box that allows setting its Document base not requiring the caller to know the exact types of the box and its base.

## Conforms To

- Scene

