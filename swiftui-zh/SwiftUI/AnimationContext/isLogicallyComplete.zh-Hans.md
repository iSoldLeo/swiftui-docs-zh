---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationContext/isLogicallyComplete
抓取时间： 2025-12-03T06:14:34Z
---

# isLogicallyComplete

**实例属性**

将此属性设置为 `true`，表示动画在逻辑上已完成。

### 声明

```swift
var isLogicallyComplete: Bool
```

## 讨论

该选项控制何时触发 AnimationCompletionCriteria.logicallyComplete 完成回调。在一个动画的生命周期中，最多只能将其设置为 `true`一次，之后再改回 `false`将被忽略。如果从未将此值设置为 `true`，则行为等同于在动画结束时将此值设置为 `true`（返回 `nil`）。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationContext/isLogicallyComplete
crawled: 2025-12-03T06:14:34Z
---

# isLogicallyComplete

**Instance Property**

Set this to `true` to indicate that an animation is logically complete.

## Declaration

```swift
var isLogicallyComplete: Bool
```

## Discussion

This controls when AnimationCompletionCriteria.logicallyComplete completion callbacks are fired. This should be set to `true` at most once in the life of an animation, changing back to `false` later will be ignored. If this is never set to `true`, the behavior is equivalent to if this had been set to `true` just as the animation finished (by returning `nil`).

