--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)

抓取时间：2025-12-01T10:30:31Z

---

# init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

创建一个视图，用于在启动与文档相关的用户体验时显示，该视图包含本地化标题、自定义操作、背景样式和辅助视图。

## 声明

```swift
init<B>(_ title: LocalizedStringKey, for contentTypes: [UTType], backgroundStyle: B, @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View) where B : ShapeStyle
```

## 参数

- **title**：用于视图标题的 title 键。

- **contentTypes**：视图可以打开的内容类型。

- **backgroundStyle**：视图的可选背景样式。

- **actions**：返回视图操作的视图构建器。

- **onDocumentOpen**：处理打开文件的闭包。

- **backgroundAccessoryView**：用于返回视图背景辅助视图的视图构建器。

- **overlayAccessoryView**：用于返回视图覆盖辅助视图的视图构建器。

## 讨论


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)
crawled: 2025-12-01T10:30:31Z
---

# init(_:for:backgroundStyle:_:onDocumentOpen:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background style, and accessory views.

## Declaration

```swift
init<B>(_ title: LocalizedStringKey, for contentTypes: [UTType], backgroundStyle: B, @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View) where B : ShapeStyle
```

## Parameters

- **title**: A title key to use for the view title.
- **contentTypes**: Content types that the view can open.
- **backgroundStyle**: An optional background style of the view.
- **actions**: A view builder returning the view’s actions
- **onDocumentOpen**: A closure that handles an open file.
- **backgroundAccessoryView**: A view builder for returning the view’s background accessory view.
- **overlayAccessoryView**: A view builder for returning the view’s overlay accessory view.

## Discussion



