--- 来源：https://developer.apple.com/documentation/SwiftUI/AnimationState/subscript(_:)

抓取时间：2025-12-03T06:14:35Z

---

# subscript(_:)

**实例 Subscript**

访问自定义键的状态。

## 声明

```swift
subscript<K>(key: K.Type) -> K.Value where K : AnimationStateKey { get set }
```

## 概述

通过定义一个符合 [AnimationStateKey](../AnimationStateKey.zh-Hans.md) 协议的键，并为该键提供 [defaultValue](../AnimationStateKey/defaultValue.zh-Hans.md)，来创建自定义动画状态值。同时，还要包含用于读取和写入 [CustomAnimation](../CustomAnimation.zh-Hans.md) 所用状态值的属性。例如，以下代码定义了一个名为 `PausableState` 的键，它有两个状态值 `paused` 和 `pauseTime`：

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

使用该键以及 [AnimationState](../AnimationState.zh-Hans.md) 结构的下标运算符来获取和设置该键的值。为了更方便地访问键值，可以扩展 [AnimationContext](../AnimationContext.zh-Hans.md)，添加一个计算属性来获取和设置键的值。

```swift
extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

要访问 [CustomAnimation](../CustomAnimation.zh-Hans.md) 中的状态值，请调用自定义计算属性，然后读取和写入自定义 [AnimationStateKey](../AnimationStateKey.zh-Hans.md) 提供的状态值。

```swift
struct PausableAnimation: CustomAnimation {
    let base: Animation

    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        let paused = context.environment.animationPaused

        let pausableState = context.pausableState
        var pauseTime = pausableState.pauseTime
        if pausableState.paused != paused {
            pauseTime = time - pauseTime
            context.pausableState = PausableState(paused: paused, pauseTime: pauseTime)
        }

        let effectiveTime = paused ? pauseTime : time - pauseTime
        let result = base.animate(value: value, time: effectiveTime, context: &context)
        return result
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationState/subscript(_:)
crawled: 2025-12-03T06:14:35Z
---

# subscript(_:)

**Instance Subscript**

Accesses the state for a custom key.

## Declaration

```swift
subscript<K>(key: K.Type) -> K.Value where K : AnimationStateKey { get set }
```

## Overview

Create a custom animation state value by defining a key that conforms to the [AnimationStateKey](../AnimationStateKey.zh-Hans.md) protocol and provide the [defaultValue](../AnimationStateKey/defaultValue.zh-Hans.md) for the key. Also include properties to read and write state values that your [CustomAnimation](../CustomAnimation.zh-Hans.md) uses. For example, the following code defines a key named `PausableState` that has two state values, `paused` and `pauseTime`:

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

Use that key with the subscript operator of the [AnimationState](../AnimationState.zh-Hans.md) structure to get and set a value for the key. For more convenient access to the key value, extend [AnimationContext](../AnimationContext.zh-Hans.md) with a computed property that gets and sets the key’s value.

```swift
extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

To access the state values in a [CustomAnimation](../CustomAnimation.zh-Hans.md), call the custom computed property, then read and write the state values that the custom [AnimationStateKey](../AnimationStateKey.zh-Hans.md) provides.

```swift
struct PausableAnimation: CustomAnimation {
    let base: Animation

    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        let paused = context.environment.animationPaused

        let pausableState = context.pausableState
        var pauseTime = pausableState.pauseTime
        if pausableState.paused != paused {
            pauseTime = time - pauseTime
            context.pausableState = PausableState(paused: paused, pauseTime: pauseTime)
        }

        let effectiveTime = paused ? pauseTime : time - pauseTime
        let result = base.animate(value: value, time: effectiveTime, context: &context)
        return result
    }
}
```

