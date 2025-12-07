---
来源: https://developer.apple.com/documentation/SwiftUI/UIViewRepresentable/sizeThatFits(_:uiView:context:)
抓取时间： 2025-12-03T05:38:53Z
---

# sizeThatFits(_:uiView:context:)

**实例方法**

给定一个建议尺寸，返回复合视图的首选尺寸。

## 声明

```swift
@MainActor @preconcurrency func sizeThatFits(_ proposal: ProposedViewSize, uiView: Self.UIViewType, context: Self.Context) -> CGSize?
```

## 参数

- **proposal**：建议的视图大小。
- **uiView**：您的自定义视图对象。
- **context**：包含系统当前状态信息的上下文结构。

## 返回值

所代表视图控制器的复合大小。如果返回值为`nil`，则表示系统应使用默认大小算法。

## 讨论

在同一布局过程中，此方法可能会被多次调用，并建议不同的大小。SwiftUI 视图可自行选择大小，因此此函数返回的值之一将始终用作复合视图的实际大小。


---
source: https://developer.apple.com/documentation/SwiftUI/UIViewRepresentable/sizeThatFits(_:uiView:context:)
crawled: 2025-12-03T05:38:53Z
---

# sizeThatFits(_:uiView:context:)

**Instance Method**

Given a proposed size, returns the preferred size of the composite view.

## Declaration

```swift
@MainActor @preconcurrency func sizeThatFits(_ proposal: ProposedViewSize, uiView: Self.UIViewType, context: Self.Context) -> CGSize?
```

## Parameters

- **proposal**: The proposed size for the view.
- **uiView**: Your custom view object.
- **context**: A context structure containing information about the current state of the system.

## Return Value

The composite size of the represented view controller. Returning a value of `nil` indicates that the system should use the default sizing algorithm.

## Discussion

This method may be called more than once with different proposed sizes during the same layout pass. SwiftUI views choose their own size, so one of the values returned from this function will always be used as the actual size of the composite view.

