---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/logicallyComplete(after:)
抓取时间： 2025-12-03T06:12:33Z
---

# logicallyComplete(after:)

**实例方法**

如果动画尚未逻辑完成，则会在指定的持续时间后报告逻辑完成。

## 声明

```swift
func logicallyComplete(after duration: TimeInterval) -> Animation
```

## 参数

- **duration**：动画报告逻辑上已完成的持续时间。

## 返回值

在给定时长后报告逻辑完成的动画。

## 讨论

请注意，在基本动画完全结束后，指定的持续时间不会导致动画继续运行。

如果动画在达到指定的持续时间之前被移除，则会立即报告逻辑完成。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/logicallyComplete(after:)
crawled: 2025-12-03T06:12:33Z
---

# logicallyComplete(after:)

**Instance Method**

Causes the animation to report logical completion after the specified duration, if it has not already logically completed.

## Declaration

```swift
func logicallyComplete(after duration: TimeInterval) -> Animation
```

## Parameters

- **duration**: The duration after which the animation should  report that it is logically complete.

## Return Value

An animation that reports logical completion after the given duration.

## Discussion

Note that the indicated duration will not cause the animation to continue running after the base animation has fully completed.

If the animation is removed before the given duration is reached, logical completion will be reported immediately.

