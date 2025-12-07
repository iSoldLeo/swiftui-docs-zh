--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomAnimation/velocity(value:time:context:)

抓取时间：2025-12-03T04:16:40Z

---

# velocity(value:time:context:)

**实例方法**

计算指定时间点的动画速度。

## 声明

```swift
nonisolated func velocity<V>(value: V, time: TimeInterval, context: AnimationContext<V>) -> V? where V : VectorArithmetic
```

## 参数

- **value**：动画方向的向量。

- **time**：动画开始至今的时间。

- **context**：[AnimationContext](../AnimationContext.zh-Hans.md) 的实例，用于访问状态和动画环境。

## 返回值

动画的当前速度，如果动画已结束，则返回 `nil`。

## 说明

实现此方法可获取动画在给定时间点的速度。如果后续动画与当前动画合并，系统会保持动画间速度的连续性。

此方法的默认实现返回 `nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomAnimation/velocity(value:time:context:)
crawled: 2025-12-03T04:16:40Z
---

# velocity(value:time:context:)

**Instance Method**

Calculates the velocity of the animation at a specified time.

## Declaration

```swift
nonisolated func velocity<V>(value: V, time: TimeInterval, context: AnimationContext<V>) -> V? where V : VectorArithmetic
```

## Parameters

- **value**: The vector to animate towards.
- **time**: The amount of time since the start of the animation.
- **context**: An instance of [AnimationContext](../AnimationContext.zh-Hans.md) that provides access to state and the animation environment.

## Return Value

The current velocity of the animation, or `nil` if the animation has finished.

## Discussion

Implement this method to provide the velocity of the animation at a given time. Should subsequent animations merge with the animation, the system preserves continuity of the velocity between animations.

The default implementation of this method returns `nil`.



