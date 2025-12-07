---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationCompletionCriteria/removed
抓取时间： 2025-12-03T06:12:03Z
---

# 已删除

**类型属性**

整个动画已经完成，现在将被移除。

## 声明

```swift
static let removed: AnimationCompletionCriteria
```

## 讨论

如果随后发生的更改在已注册`removed` 完成回调的属性上创建了额外的动画，那么这些回调只有在*所有*创建的动画都完成时才会触发。

## 获取完成条件

- **logicallyComplete**：动画在逻辑上已完成，但可能仍处于长尾阶段。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationCompletionCriteria/removed
crawled: 2025-12-03T06:12:03Z
---

# removed

**Type Property**

The entire animation is finished and will now be removed.

## Declaration

```swift
static let removed: AnimationCompletionCriteria
```

## Discussion

If a subsequent change occurs that creates additional animations on properties with `removed` completion callbacks registered, then those callbacks will only fire when *all* of the created animations are complete.

## Getting the completion criteria

- **logicallyComplete**: The animation has logically completed, but may still be in its long tail.

