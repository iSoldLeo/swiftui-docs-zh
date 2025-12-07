---
来源： https://developer.apple.com/documentation/SwiftUI/UIViewControllerRepresentable/dismantleUIViewController(_:coordinator:)
抓取时间： 2025-12-03T05:38:36Z
---

# dismantleUIViewController(_:coordinator:)

**类型方法**

清理显示的视图控制器（和协调器），以备移除。

## 声明

```swift
@MainActor @preconcurrency static func dismantleUIViewController(_ uiViewController: Self.UIViewControllerType, coordinator: Self.Coordinator)
```

## 参数

- **uiViewController**：您的自定义视图控制器对象。
- **coordinator**：您的自定义视图控制器对象：您用来将更改传回 SwiftUI 的自定义协调器实例。如果不使用自定义协调器，系统会提供一个默认实例。

## 讨论

使用此方法可执行与自定义视图控制器相关的其他清理工作。例如，您可以使用此方法删除观察者或更新 SwiftUI 界面的其他部分。


---
source: https://developer.apple.com/documentation/SwiftUI/UIViewControllerRepresentable/dismantleUIViewController(_:coordinator:)
crawled: 2025-12-03T05:38:36Z
---

# dismantleUIViewController(_:coordinator:)

**Type Method**

Cleans up the presented view controller (and coordinator) in anticipation of their removal.

## Declaration

```swift
@MainActor @preconcurrency static func dismantleUIViewController(_ uiViewController: Self.UIViewControllerType, coordinator: Self.Coordinator)
```

## Parameters

- **uiViewController**: Your custom view controller object.
- **coordinator**: The custom coordinator instance you use to communicate changes back to SwiftUI. If you do not use a custom coordinator, the system provides a default instance.

## Discussion

Use this method to perform additional clean-up work related to your custom view controller. For example, you might use this method to remove observers or update other parts of your SwiftUI interface.

