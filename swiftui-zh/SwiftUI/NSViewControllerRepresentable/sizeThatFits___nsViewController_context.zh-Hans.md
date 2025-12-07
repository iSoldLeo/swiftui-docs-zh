---
来源：https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentable/sizeThatFits(_:nsViewController:context:)
抓取时间：2025-12-01T10:26:54Z
---

# sizeThatFits(_:nsViewController:context:)

**实例方法**

给定一个建议的大小，返回复合视图的首选大小。

## 声明

```swift
@MainActor @preconcurrency func sizeThatFits(_ proposal: ProposedViewSize, nsViewController: Self.NSViewControllerType, context: Self.Context) -> CGSize?
```

## 参数

- **proposal**：视图控制器的建议大小。
- **nsViewController**：您的自定义视图控制器对象。
- **context**：包含系统当前状态信息的上下文结构。

## 返回值

所代表视图控制器的复合大小。如果返回值为`nil`，则表示系统应使用默认大小算法。

## 讨论

在同一布局过程中，此方法可能会被多次调用，并建议不同的大小。SwiftUI 视图可自行选择大小，因此此函数返回的值之一将始终用作复合视图的实际大小。


---
source: https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentable/sizeThatFits(_:nsViewController:context:)
crawled: 2025-12-01T10:26:54Z
---

# sizeThatFits(_:nsViewController:context:)

**Instance Method**

Given a proposed size, returns the preferred size of the composite view.

## Declaration

```swift
@MainActor @preconcurrency func sizeThatFits(_ proposal: ProposedViewSize, nsViewController: Self.NSViewControllerType, context: Self.Context) -> CGSize?
```

## Parameters

- **proposal**: The proposed size for the view controller.
- **nsViewController**: Your custom view controller object.
- **context**: A context structure containing information about the current state of the system.

## Return Value

The composite size of the represented view controller. Returning a value of `nil` indicates that the system should use the default sizing algorithm.

## Discussion

This method may be called more than once with different proposed sizes during the same layout pass. SwiftUI views choose their own size, so one of the values returned from this function will always be used as the actual size of the composite view.

