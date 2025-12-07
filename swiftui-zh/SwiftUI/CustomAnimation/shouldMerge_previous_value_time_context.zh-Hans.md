--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomAnimation/shouldMerge(previous:value:time:context:)

抓取时间：2025-12-01T09:06:07Z

---

# shouldMerge(previous:value:time:context:)

**实例方法**

确定动画实例是否可以与同一类型的另一个实例合并。

## 声明

```swift
nonisolated func shouldMerge<V>(previous: Animation, value: V, time: TimeInterval, context: inout AnimationContext<V>) -> Bool where V : VectorArithmetic
```

## 参数

- **previous**：上一个正在运行的动画。

- **value**：动画要指向的向量。

- **time**：自上一个动画开始以来经过的时间。

- **context**：[AnimationContext](../AnimationContext.zh-Hans.md) 的一个实例，提供对状态和动画环境的访问。

## 返回值

如果动画应与之前的动画合并，则返回布尔值 `true`；否则，返回 `false`。

## 说明

当视图在一个可动画值上创建一个新动画，而该值已经有一个相同类型的动画正在运行时，系统会调用新实例上的 `shouldMerge(previous:value:time:context:)` 方法来确定是否可以合并这两个实例。如果动画可以与另一个实例合并，则实现此方法。默认实现返回 `false`。

如果 `shouldMerge(previous:value:time:context:)` 返回 `true`，则系统会将新的动画实例与之前的动画合并。系统会将前一个实例的状态和运行时间传递给新实例，然后移除之前的动画。

如果此方法返回 `false`，则系统不会将新旧动画合并。相反，两个动画会同时运行，系统会合并它们的结果。

如果您的自定义动画需要在调用 `shouldMerge(previous:value:time:context:)` 方法之间保持状态，请将状态数据存储在 `context` 中。这样，下次系统调用该方法时，数据即可被访问。要了解更多信息，请参阅 [AnimationContext](../AnimationContext.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomAnimation/shouldMerge(previous:value:time:context:)
crawled: 2025-12-01T09:06:07Z
---

# shouldMerge(previous:value:time:context:)

**Instance Method**

Determines whether an instance of the animation can merge with other instance of the same type.

## Declaration

```swift
nonisolated func shouldMerge<V>(previous: Animation, value: V, time: TimeInterval, context: inout AnimationContext<V>) -> Bool where V : VectorArithmetic
```

## Parameters

- **previous**: The previous running animation.
- **value**: The vector to animate towards.
- **time**: The amount of time since the start of the previous animation.
- **context**: An instance of [AnimationContext](../AnimationContext.zh-Hans.md) that provides access to state and the animation environment.

## Return Value

A Boolean value of `true` if the animation should merge with the previous animation; otherwise, `false`.

## Discussion

When a view creates a new animation on an animatable value that already has a running animation of the same animation type, the system calls the `shouldMerge(previous:value:time:context:)` method on the new instance to determine whether it can merge the two instance. Implement this method if the animation can merge with another instance. The default implementation returns `false`.

If `shouldMerge(previous:value:time:context:)` returns `true`, the system merges the new animation instance with the previous animation. The system provides to the new instance the state and elapsed time from the previous one. Then it removes the previous animation.

If this method returns `false`, the system doesn’t merge the animation with the previous one. Instead, both animations run together and the system combines their results.

If your custom animation needs to maintain state between calls to the `shouldMerge(previous:value:time:context:)` method, store the state data in `context`. This makes the data available to the method next time the system calls it. To learn more, see [AnimationContext](../AnimationContext.zh-Hans.md).

