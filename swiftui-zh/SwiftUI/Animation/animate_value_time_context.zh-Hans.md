---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/animate(value:time:context:)
抓取时间：2025-12-01T11:01:39Z
---

# animate(value:time:context:)

**实例方法**

计算动画的当前值。

## 声明

```swift
func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic
```

## 返回值

动画的当前值，如果动画已结束，则返回 `nil` 。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/animate(value:time:context:)
crawled: 2025-12-01T11:01:39Z
---

# animate(value:time:context:)

**Instance Method**

Calculates the current value of the animation.

## Declaration

```swift
func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic
```

## Return Value

The current value of the animation, or `nil` if the animation has finished.

