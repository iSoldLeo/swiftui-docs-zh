---
来源： https://developer.apple.com/documentation/SwiftUI/UIViewRepresentable/dismantleUIView(_:coordinator:)
抓取时间： 2025-12-03T05:38:54Z
---

# dismantleUIView(_:coordinator:)

**类型方法**

清理显示的 UIKit 视图（和协调器），以备移除。

## 声明

```swift
@MainActor @preconcurrency static func dismantleUIView(_ uiView: Self.UIViewType, coordinator: Self.Coordinator)
```

## 参数

- **uiView**：您的自定义视图对象。
- **coordinator**：您的自定义视图对象：用于将更改传回 SwiftUI 的自定义协调器实例。如果不使用自定义协调器，系统会提供一个默认实例。

## 讨论

使用此方法可执行与自定义视图相关的其他清理工作。例如，您可以使用此方法删除观察者或更新 SwiftUI 界面的其他部分。


---
source: https://developer.apple.com/documentation/SwiftUI/UIViewRepresentable/dismantleUIView(_:coordinator:)
crawled: 2025-12-03T05:38:54Z
---

# dismantleUIView(_:coordinator:)

**Type Method**

Cleans up the presented UIKit view (and coordinator) in anticipation of their removal.

## Declaration

```swift
@MainActor @preconcurrency static func dismantleUIView(_ uiView: Self.UIViewType, coordinator: Self.Coordinator)
```

## Parameters

- **uiView**: Your custom view object.
- **coordinator**: The custom coordinator instance you use to communicate changes back to SwiftUI. If you do not use a custom coordinator, the system provides a default instance.

## Discussion

Use this method to perform additional clean-up work related to your custom view. For example, you might use this method to remove observers or update other parts of your SwiftUI interface.

