--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:overlayAccessoryView:)

抓取时间：2025-12-01T10:30:29Z

---

# init(_:for:_:onDocumentOpen:overlayAccessoryView:)

**Initializer**

创建一个视图，用于在启动与文档相关的用户体验时显示，该视图包含本地化标题、自定义操作和覆盖式辅助视图。

## 声明

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## 参数

- **title**：用于视图标题的 title 键。

- **contentTypes**：视图可以打开的内容类型。

- **actions**：返回视图操作的视图构建器

- **onDocumentOpen**：处理打开文件的闭包

- **overlayAccessoryView**：返回视图的覆盖辅助视图的视图构建器

## 讨论


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:overlayAccessoryView:)
crawled: 2025-12-01T10:30:29Z
---

# init(_:for:_:onDocumentOpen:overlayAccessoryView:)

**Initializer**

Creates a view to present when launching document-related user experiences using a localized title, custom actions, and an overlay accessory view.

## Declaration

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder overlayAccessoryView: @escaping (DocumentLaunchGeometryProxy) -> some View)
```

## Parameters

- **title**: A title key to use for the view title.
- **contentTypes**: Content types that the view can open.
- **actions**: A view builder returning the view’s actions
- **onDocumentOpen**: A closure that handles an open file.
- **overlayAccessoryView**: A view builder for returning the view’s overlay accessory view.

## Discussion



