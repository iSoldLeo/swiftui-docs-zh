---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationCompletionCriteria/logicallyComplete
抓取时间： 2025-12-03T06:12:02Z
---

# logicallyComplete

**类型属性**

动画在逻辑上已完成，但可能仍处于长尾阶段。

## 声明

```swift
static let logicallyComplete: AnimationCompletionCriteria
```

## 讨论

如果随后发生的更改在已注册`logicallyComplete` 完成回调的属性上创建了额外的动画，那么这些回调将在它们所注册的更改的动画逻辑上完成时触发，而忽略新的动画。

## 获取完成标准

- **removed**：整个动画已完成，现在将被移除。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationCompletionCriteria/logicallyComplete
crawled: 2025-12-03T06:12:02Z
---

# logicallyComplete

**Type Property**

The animation has logically completed, but may still be in its long tail.

## Declaration

```swift
static let logicallyComplete: AnimationCompletionCriteria
```

## Discussion

If a subsequent change occurs that creates additional animations on properties with `logicallyComplete` completion callbacks registered, then those callbacks will fire when the animations from the change that they were registered with logically complete, ignoring the new animations.

## Getting the completion criteria

- **removed**: The entire animation is finished and will now be removed.

