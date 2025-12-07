---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/tracksVelocity
抓取时间： 2025-12-03T06:17:24Z
---

# tracksVelocity

**实例属性**

此事务是否会跟踪任何可改变的动画属性的速度。

## 声明

```swift
var tracksVelocity: Bool { get set }
```

## 讨论

此属性可在交互式上下文中启用，以便在用户交互过程中跟踪速度，这样当交互结束时，动画就可以使用累积的速度来创建动画，并保持这些速度。这种跟踪与视图变化时使用的动画是相互排斥的，因为如果有一个动画，它就会负责管理自己的速度。

手势 onChanged 和更新回调会自动将此属性设置为 true。

本示例展示了一个交互，该交互应用变化，跟踪速度直到最后的变化，最后的变化应用动画（动画将以之前变化时跟踪的速度开始）。这些变化可能来自服务器，也可能来自滑块等交互式控件。

```swift
func receiveChange(change: ChangeInfo) {
    var transaction = Transaction()
    if change.isFinal {
        transaction.animation = .spring
    } else {
        transaction.tracksVelocity = true
    }
    withTransaction(transaction) {
        state.applyChange(change)
    }
}
```

## 获取事务信息

- **isContinuous**：布尔值，表示事务是否源于产生一连串值的操作。
- **scrollTargetAnchor**：滚动到视图时，视图在滚动视图可见区域内的首选对齐方式。
- **subscript(_:)**：访问与自定义键关联的事务值。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/tracksVelocity
crawled: 2025-12-03T06:17:24Z
---

# tracksVelocity

**Instance Property**

Whether this transaction will track the velocity of any animatable properties that change.

## Declaration

```swift
var tracksVelocity: Bool { get set }
```

## Discussion

This property can be enabled in an interactive context to track velocity during a user interaction so that when the interaction ends, an animation can use the accumulated velocities to create animations that preserve them. This tracking is mutually exclusive with an animation being used during a view change, since if there is an animation, it is responsible for managing its own velocity.

Gesture onChanged and updating callbacks automatically set this property to true.

This example shows an interaction which applies changes, tracking velocity until the final change, which applies an animation (which will start with the velocity that was tracked during the previous changes). These changes could come from a server or from an interactive control like a slider.

```swift
func receiveChange(change: ChangeInfo) {
    var transaction = Transaction()
    if change.isFinal {
        transaction.animation = .spring
    } else {
        transaction.tracksVelocity = true
    }
    withTransaction(transaction) {
        state.applyChange(change)
    }
}
```

## Getting information about a transaction

- **isContinuous**: A Boolean value that indicates whether the transaction originated from an action that produces a sequence of values.
- **scrollTargetAnchor**: The preferred alignment of the view within a scroll view’s visible region when scrolling to a view.
- **subscript(_:)**: Accesses the transaction value associated with a custom key.

