--- 来源：https://developer.apple.com/documentation/SwiftUI/AnimationState
抓取时间：2025-12-02T17:34:01Z

---

# AnimationState

**Structure**

用于存储自定义动画状态的容器。

## 声明

```swift
struct AnimationState<Value> where Value : VectorArithmetic
```

## 概述

[AnimationContext](AnimationContext.zh-Hans.md) 使用此类型存储 [CustomAnimation](CustomAnimation.zh-Hans.md) 的状态。要检索上下文的已存储状态，可以使用 [state](AnimationContext/state.zh-Hans.md) 属性。然而，访问动画状态更便捷的方法是定义一个 [AnimationStateKey](AnimationStateKey.zh-Hans.md)，并扩展 [AnimationContext](AnimationContext.zh-Hans.md)，添加一个用于获取和设置动画状态的计算属性，如下面的代码所示：

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    static var defaultValue: Self { .init() }
}

extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

创建 [AnimationStateKey](AnimationStateKey.zh-Hans.md) 时，最好定义自定义动画所需的状态值。例如，以下代码将属性 `paused` 和 `pauseTime` 添加到 `PausableState` 动画状态键：

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

要访问 `PausableAnimation` 中的可暂停状态，以下代码调用 `pausableState` 而不是使用上下文的 [state](AnimationContext/state.zh-Hans.md) 属性。由于动画状态键 `PausableState` 定义了状态值的属性，因此自定义动画可以读取和写入这些值。

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

### 存储辅助动画的状态

自定义动画还可以使用 `AnimationState` 来存储辅助动画的状态。例如，以下代码创建了一个包含属性 `secondaryState` 的 [AnimationStateKey](AnimationStateKey.zh-Hans.md)，自定义动画可以使用该属性来存储其他状态：

```swift
private struct TargetState<Value: VectorArithmetic>: AnimationStateKey {
    var timeDelta = 0.0
    var valueDelta = Value.zero
    var secondaryState: AnimationState<Value>? = .init()

    static var defaultValue: Self { .init() }
}

extension AnimationContext {
    fileprivate var targetState: TargetState<Value> {
        get { state[TargetState<Value>.self] }
        set { state[TargetState<Value>.self] = newValue }
    }
}
```

自定义动画 `TargetAnimation` 使用 `TargetState` 将状态数据存储在 `secondaryState` 中，用于作为目标动画一部分运行的另一个动画。

```swift
struct TargetAnimation: CustomAnimation {
    var base: Animation
    var secondary: Animation

    func animate<V: VectorArithmetic>(value: V, time: Double, context: inout AnimationContext<V>) -> V? {
        var targetValue = value
        if let secondaryState = context.targetState.secondaryState {
            var secondaryContext = context
            secondaryContext.state = secondaryState
            let secondaryValue = value - context.targetState.valueDelta
            let result = secondary.animate(
                value: secondaryValue, time: time - context.targetState.timeDelta,
                context: &secondaryContext)
            if let result = result {
                context.targetState.secondaryState = secondaryContext.state
                targetValue = result + context.targetState.valueDelta
            } else {
                context.targetState.secondaryState = nil
            }
        }
        let result = base.animate(value: targetValue, time: time, context: &context)
        if let result = result {
            targetValue = result
        } else if context.targetState.secondaryState == nil {
            return nil
        }
        return targetValue
}

    func shouldMerge<V: VectorArithmetic>(previous: Animation, value: V, time: Double, context: inout AnimationContext<V>) -> Bool {
        guard let previous = previous.base as? Self else { return false }
        var secondaryContext = context
        if let secondaryState = context.targetState.secondaryState {
            secondaryContext.state = secondaryState
            context.targetState.valueDelta = secondary.animate(
                value: value, time: time - context.targetState.timeDelta,
                context: &secondaryContext) ?? value
        } else {
            context.targetState.valueDelta = value
        }
        // Reset the target each time a merge occurs.
        context.targetState.secondaryState = .init()
        context.targetState.timeDelta = time
        return base.shouldMerge(
            previous: previous.base, value: value, time: time,
            context: &context)
    }
}
```

## 创建动画状态

- **init()**：创建一个空的状态容器。

## 访问自定义键

- **subscript(_:)**：访问自定义键的状态。

## 创建自定义动画

- **CustomAnimation**：定义可动画值随时间变化方式的类型。

- **AnimationContext**：自定义动画可用于管理状态和访问视图环境的上下文值。

- **AnimationStateKey**：用于访问动画状态值的键。

- **UnitCurve**：由二维曲线定义的函数，该函数将 [0,1] 范围内的输入进度映射到 [0,1] 范围内的输出进度。通过改变曲线的形状，可以改变动画或其他插值动画的有效速度。

- **Spring**：弹簧运动的表示。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationState
crawled: 2025-12-02T17:34:01Z
---

# AnimationState

**Structure**

A container that stores the state for a custom animation.

## Declaration

```swift
struct AnimationState<Value> where Value : VectorArithmetic
```

## Overview

An [AnimationContext](AnimationContext.zh-Hans.md) uses this type to store state for a [CustomAnimation](CustomAnimation.zh-Hans.md). To retrieve the stored state of a context, you can use the [state](AnimationContext/state.zh-Hans.md) property. However, a more convenient way to access the animation state is to define an [AnimationStateKey](AnimationStateKey.zh-Hans.md) and extend [AnimationContext](AnimationContext.zh-Hans.md) with a computed property that gets and sets the animation state, as shown in the following code:

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    static var defaultValue: Self { .init() }
}

extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

When creating an [AnimationStateKey](AnimationStateKey.zh-Hans.md), it’s convenient to define the state values that your custom animation needs. For example, the following code adds the properties `paused` and `pauseTime` to the `PausableState` animation state key:

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

To access the pausable state in a `PausableAnimation`, the follow code calls `pausableState` instead of using the context’s [state](AnimationContext/state.zh-Hans.md) property. And because the animation state key `PausableState` defines properties for state values, the custom animation can read and write those values.

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

### Storing state for secondary animations

A custom animation can also use `AnimationState` to store the state of a secondary animation. For example, the following code creates an [AnimationStateKey](AnimationStateKey.zh-Hans.md) that includes the property `secondaryState`, which a custom animation can use to store other state:

```swift
private struct TargetState<Value: VectorArithmetic>: AnimationStateKey {
    var timeDelta = 0.0
    var valueDelta = Value.zero
    var secondaryState: AnimationState<Value>? = .init()

    static var defaultValue: Self { .init() }
}

extension AnimationContext {
    fileprivate var targetState: TargetState<Value> {
        get { state[TargetState<Value>.self] }
        set { state[TargetState<Value>.self] = newValue }
    }
}
```

The custom animation `TargetAnimation` uses `TargetState` to store state data in `secondaryState` for another animation that runs as part of the target animation.

```swift
struct TargetAnimation: CustomAnimation {
    var base: Animation
    var secondary: Animation

    func animate<V: VectorArithmetic>(value: V, time: Double, context: inout AnimationContext<V>) -> V? {
        var targetValue = value
        if let secondaryState = context.targetState.secondaryState {
            var secondaryContext = context
            secondaryContext.state = secondaryState
            let secondaryValue = value - context.targetState.valueDelta
            let result = secondary.animate(
                value: secondaryValue, time: time - context.targetState.timeDelta,
                context: &secondaryContext)
            if let result = result {
                context.targetState.secondaryState = secondaryContext.state
                targetValue = result + context.targetState.valueDelta
            } else {
                context.targetState.secondaryState = nil
            }
        }
        let result = base.animate(value: targetValue, time: time, context: &context)
        if let result = result {
            targetValue = result
        } else if context.targetState.secondaryState == nil {
            return nil
        }
        return targetValue
}

    func shouldMerge<V: VectorArithmetic>(previous: Animation, value: V, time: Double, context: inout AnimationContext<V>) -> Bool {
        guard let previous = previous.base as? Self else { return false }
        var secondaryContext = context
        if let secondaryState = context.targetState.secondaryState {
            secondaryContext.state = secondaryState
            context.targetState.valueDelta = secondary.animate(
                value: value, time: time - context.targetState.timeDelta,
                context: &secondaryContext) ?? value
        } else {
            context.targetState.valueDelta = value
        }
        // Reset the target each time a merge occurs.
        context.targetState.secondaryState = .init()
        context.targetState.timeDelta = time
        return base.shouldMerge(
            previous: previous.base, value: value, time: time,
            context: &context)
    }
}
```

## Creating animation state

- **init()**: Create an empty state container.

## Accessing custom keys

- **subscript(_:)**: Accesses the state for a custom key.

## Creating custom animations

- **CustomAnimation**: A type that defines how an animatable value changes over time.
- **AnimationContext**: Contextual values that a custom animation can use to manage state and access a view’s environment.
- **AnimationStateKey**: A key for accessing animation state values.
- **UnitCurve**: A  function defined by a two-dimensional curve that maps an input progress in the range [0,1] to an output progress that is also in the range [0,1]. By changing the shape of the curve, the effective speed of an animation or other interpolation can be changed.
- **Spring**: A representation of a spring’s motion.

