--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:background:)

抓取时间：2025-12-03T05:41:16Z

---

# init(_:for:_:onDocumentOpen:background:)

**Initializer**

创建一个视图，用于在启动与文档相关的用户体验时显示，该视图包含本地化标题、自定义操作和背景视图。

## 声明

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder background: () -> some View)
```

## 参数

- **title**：用于视图标题的 title 键。

- **contentTypes**：视图可以打开的内容类型。

- **actions**：返回视图操作的视图构建器

- **onDocumentOpen**：处理打开文件的闭包

- **background**：视图的背景

## 讨论


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:background:)
crawled: 2025-12-03T05:41:16Z
---

# init(_:for:_:onDocumentOpen:background:)

**Initializer**

Creates a view to present when launching document-related user experiences using a localized title, custom actions, and a background view.

## Declaration

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView, @ViewBuilder background: () -> some View)
```

## Parameters

- **title**: A title key to use for the view title.
- **contentTypes**: Content types that the view can open.
- **actions**: A view builder returning the view’s actions
- **onDocumentOpen**: A closure that handles an open file.
- **background**: A background of the view.

## Discussion



