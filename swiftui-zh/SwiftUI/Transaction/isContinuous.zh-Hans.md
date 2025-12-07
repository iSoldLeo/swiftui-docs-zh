---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/isContinuous
抓取时间： 2025-12-03T06:17:23Z
---

# isContinuous

**实例属性**

布尔值，用于指示事务是否源于产生一连串值的操作。

## 声明

```swift
var isContinuous: Bool { get set }
```

## 讨论

如果是连续操作创建了事务，该值为`true`，否则为`false`。连续操作包括拖动滑块或按住步进器，而不是点击按钮。

## 获取事务信息

- **scrollTargetAnchor**：当滚动到一个视图时，视图在滚动视图可见区域内的首选对齐方式。
- **tracksVelocity**：该事务是否会跟踪任何动画属性变化的速度。
- **subscript(_:)**：访问与自定义键关联的事务值。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/isContinuous
crawled: 2025-12-03T06:17:23Z
---

# isContinuous

**Instance Property**

A Boolean value that indicates whether the transaction originated from an action that produces a sequence of values.

## Declaration

```swift
var isContinuous: Bool { get set }
```

## Discussion

This value is `true` if a continuous action created the transaction, and is `false` otherwise. Continuous actions include things like dragging a slider or pressing and holding a stepper, as opposed to tapping a button.

## Getting information about a transaction

- **scrollTargetAnchor**: The preferred alignment of the view within a scroll view’s visible region when scrolling to a view.
- **tracksVelocity**: Whether this transaction will track the velocity of any animatable properties that change.
- **subscript(_:)**: Accesses the transaction value associated with a custom key.

