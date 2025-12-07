--- 来源：https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:)

抓取时间：2025-12-03T05:41:15Z

---

# init(_:for:_:onDocumentOpen:)

**Initializer**

创建一个视图，用于在启动与文档相关的用户体验时显示，该视图具有本地化标题和自定义操作。

## 声明

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView)
```

## 参数

- **title**：用于视图标题的 title 键。

- **contentTypes**：视图可以打开的内容类型。

- **actions**：返回视图操作的视图构建器

- **onDocumentOpen**：处理已打开文件的闭包

## 讨论


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentLaunchView/init(_:for:_:onDocumentOpen:)
crawled: 2025-12-03T05:41:15Z
---

# init(_:for:_:onDocumentOpen:)

**Initializer**

Creates a view to present when launching document-related user experiences using a localized title and custom actions.

## Declaration

```swift
init(_ title: LocalizedStringKey, for contentTypes: [UTType], @ViewBuilder _ actions: () -> Actions, @ViewBuilder onDocumentOpen: @escaping (URL) -> DocumentView)
```

## Parameters

- **title**: A title key to use for the view title.
- **contentTypes**: Content types that the view can open.
- **actions**: A view builder returning the view’s actions
- **onDocumentOpen**: A closure that handles an open file.

## Discussion



