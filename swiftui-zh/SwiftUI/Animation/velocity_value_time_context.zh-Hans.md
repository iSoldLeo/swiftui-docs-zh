---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/velocity(value:time:context:)
抓取时间：2025-12-03T06:12:34Z
---

# velocity(value:time:context:)

**实例方法**

计算动画的当前速度。

## 声明

```swift
func velocity<V>(value: V, time: TimeInterval, context: AnimationContext<V>) -> V? where V : VectorArithmetic
```

## 返回值

动画的当前速度，如果没有速度，则返回 `nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/velocity(value:time:context:)
crawled: 2025-12-03T06:12:34Z
---

# velocity(value:time:context:)

**Instance Method**

Calculates the current velocity of the animation.

## Declaration

```swift
func velocity<V>(value: V, time: TimeInterval, context: AnimationContext<V>) -> V? where V : VectorArithmetic
```

## Return Value

The current velocity of the animation, or `nil` if the velocity isn’t available.

