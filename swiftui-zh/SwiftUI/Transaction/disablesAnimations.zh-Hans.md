---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/disablesAnimations
抓取时间：2025-12-03T06:17:20Z
---

# disablesAnimations

**实例属性**

布尔值，表示视图是否应禁用动画。

## 声明

```swift
var disablesAnimations: Bool { get set }
```

## 讨论

在两部分转换更新的初始阶段，该值为`true`，以防止[animation(_:)](../View/animation.zh-Hans.md) 在事务中插入新动画。

## 管理动画

- **animation**：与当前状态变化相关的动画（如果有）。
- **addAnimationCompletion(criteria:_:)**：添加一个完成，以便在此事务创建的动画全部完成时运行。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/disablesAnimations
crawled: 2025-12-03T06:17:20Z
---

# disablesAnimations

**Instance Property**

A Boolean value that indicates whether views should disable animations.

## Declaration

```swift
var disablesAnimations: Bool { get set }
```

## Discussion

This value is `true` during the initial phase of a two-part transition update, to prevent [animation(_:)](../View/animation.zh-Hans.md) from inserting new animations into the transaction.

## Managing animations

- **animation**: The animation, if any, associated with the current state change.
- **addAnimationCompletion(criteria:_:)**: Adds a completion to run when the animations created with this transaction are all complete.

