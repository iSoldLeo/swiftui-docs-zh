--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:overlayAccessoryView:)

抓取时间：2025-12-01T10:30:26Z

---

# init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

创建一个视图，用于在启动与文档相关的用户体验时显示，该视图包含本地化标题、自定义操作、背景视图和辅助视图。

## 声明

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder background: () -> some View, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## 参数

- **title**：用于视图标题的 title 键。

- **contentTypes**：视图可以打开的内容类型。

- **actions**：返回视图操作的视图构建器。

- **onDocumentOpen**：处理已打开文件的闭包。

- **background**：视图的背景。

- **backgroundAccessoryView**：用于返回视图背景辅助视图的视图构建器。

- **overlayAccessoryView**：用于返回视图覆盖辅助视图的视图构建器。

## 讨论


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:overlayAccessoryView:)
crawled: 2025-12-01T10:30:26Z
---

# init(_:for:_:onDocumentOpen:background:backgroundAccessoryView:overlayAccessoryView:)

**Initializer**

Creates a view to present when launching document-related user experiences using a localized title, custom actions, a background view, and accessory views.

## Declaration

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder background: () -> some View, @ViewBuilder backgroundAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## Parameters

- **title**: A title key to use for the view title.
- **contentTypes**: Content types that the view can open.
- **actions**: A view builder returning the view’s actions
- **onDocumentOpen**: A closure that handles an open file.
- **background**: A background of the view.
- **backgroundAccessoryView**: A view builder for returning the view’s background accessory view.
- **overlayAccessoryView**: A view builder for returning the view’s overlay accessory view.

## Discussion



