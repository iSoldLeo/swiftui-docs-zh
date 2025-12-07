--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomAnimation/animate(value:time:context:)

抓取时间：2025-12-01T09:06:06Z

---

# animate(value:time:context:)

**实例方法**

计算指定时间点的动画值。

## 声明

```swift
nonisolated func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic
```

## 参数

- **value**：动画的目标向量。

- **time**：动画开始至今经过的时间。

- **context**：[AnimationContext](../AnimationContext.zh-Hans.md) 的实例，用于访问状态和动画环境。

## 返回值

动画的当前值，如果动画已结束，则返回 `nil`。

## 说明

实现此方法以计算并返回动画在给定时间点的值。如果动画已结束，则返回 `nil` 作为值。这会向系统发出信号，表明可以移除该动画。

如果您的自定义动画需要在调用 `animate(value:time:context:)` 方法之间保持状态，请将状态数据存储在 `context` 中。这样，下次系统调用该方法时，即可使用该数据。要了解有关在自定义动画中管理状态数据的更多信息，请参阅 [AnimationContext](../AnimationContext.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomAnimation/animate(value:time:context:)
crawled: 2025-12-01T09:06:06Z
---

# animate(value:time:context:)

**Instance Method**

Calculates the value of the animation at the specified time.

## Declaration

```swift
nonisolated func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic
```

## Parameters

- **value**: The vector to animate towards.
- **time**: The elapsed time since the start of the animation.
- **context**: An instance of [AnimationContext](../AnimationContext.zh-Hans.md) that provides access to state and the animation environment.

## Return Value

The current value of the animation, or `nil` if the animation has finished.

## Discussion

Implement this method to calculate and return the value of the animation at a given point in time. If the animation has finished, return `nil` as the value. This signals to the system that it can remove the animation.

If your custom animation needs to maintain state between calls to the `animate(value:time:context:)` method, store the state data in `context`. This makes the data available to the method next time the system calls it. To learn more about managing state data in a custom animation, see [AnimationContext](../AnimationContext.zh-Hans.md).

