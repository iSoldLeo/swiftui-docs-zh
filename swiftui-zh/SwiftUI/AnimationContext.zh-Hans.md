---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationContext
抓取时间：2025-12-02T17:34:00Z
---

# 动画上下文

**Structure**

自定义动画可用于管理状态和访问视图环境的上下文值。

## 声明

```swift
struct AnimationContext<Value> where Value : VectorArithmetic
```

## 概览

系统为[CustomAnimation](CustomAnimation.zh-Hans.md) 实例提供了一个`AnimationContext`，这样动画就可以存储和检索[AnimationState](AnimationState.zh-Hans.md) 实例中的值。要访问这些值，请使用上下文的 [state](AnimationContext/state.zh-Hans.md) 属性。

为了更方便地访问状态，可以创建一个 [AnimationStateKey](AnimationStateKey.zh-Hans.md) 并扩展 `AnimationContext` 以包含一个计算属性，用于获取和设置 [AnimationState](AnimationState.zh-Hans.md) 值。然后使用该属性代替 [state](AnimationContext/state.zh-Hans.md) 来检索自定义动画的状态。例如，下面的代码创建了一个名为`PausableState` 的动画状态键。然后，代码扩展了 `AnimationContext` 以包含 `pausableState` 属性：

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}

extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```属性

要访问可暂停状态，自定义动画 `PausableAnimation` 使用 `pausableState` 属性而不是 [state](AnimationContext/state.zh-Hans.md) 属性：

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
```属性

动画还可以检索创建动画的视图的环境值。要检索视图的环境值，请使用上下文的 [environment](AnimationContext/environment.zh-Hans.md) 属性。例如，下面的代码创建了一个名为`animationPaused`的自定义[EnvironmentValues](EnvironmentValues.zh-Hans.md)属性，视图`PausableAnimationView`使用该属性存储暂停状态：

```swift
extension EnvironmentValues {
    @Entry var animationPaused: Bool = false
}

struct PausableAnimationView: View {
    @State private var paused = false

    var body: some View {
        VStack {
            ...
        }
        .environment(\.animationPaused, paused)
    }
}
```

然后，自定义动画`PausableAnimation` 使用[environment](AnimationContext/environment.zh-Hans.md) 属性从视图环境中获取暂停状态：

```swift
struct PausableAnimation: CustomAnimation {
    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        let paused = context.environment.animationPaused
        ...
    }
}
```

## 管理状态

- **state**：自定义动画的当前状态。

## 读取视图环境值

- **environment**：创建自定义动画的视图的当前环境。

## 创建上下文

- **withState(_:)**：根据您提供的状态从另一个上下文创建一个新的上下文。

### 实例属性

- **isLogicallyComplete**：设置为 `true`，表示动画在逻辑上已经完成。

## 创建自定义动画

- **CustomAnimation**：一种定义动画值如何随时间变化的类型。
- **AnimationState**：用于存储自定义动画状态的容器。
- **AnimationStateKey**：用于访问动画状态值的键。
- **UnitCurve**：由二维曲线定义的函数，用于将范围为 [0,1] 的输入进度映射到范围同样为 [0,1] 的输出进度。通过改变曲线的形状，可以改变动画或其他插值的有效速度。
- **Spring**：弹簧运动的表示。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationContext
crawled: 2025-12-02T17:34:00Z
---

# AnimationContext

**Structure**

Contextual values that a custom animation can use to manage state and access a view’s environment.

## Declaration

```swift
struct AnimationContext<Value> where Value : VectorArithmetic
```

## Overview

The system provides an `AnimationContext` to a [CustomAnimation](CustomAnimation.zh-Hans.md) instance so that the animation can store and retrieve values in an instance of [AnimationState](AnimationState.zh-Hans.md). To access these values, use the context’s [state](AnimationContext/state.zh-Hans.md) property.

For more convenient access to state, create an [AnimationStateKey](AnimationStateKey.zh-Hans.md) and extend `AnimationContext` to include a computed property that gets and sets the [AnimationState](AnimationState.zh-Hans.md) value. Then use this property instead of [state](AnimationContext/state.zh-Hans.md) to retrieve the state of a custom animation. For example, the following code creates an animation state key named `PausableState`. Then the code extends `AnimationContext` to include the `pausableState` property:

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}

extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

To access the pausable state, the custom animation `PausableAnimation` uses the `pausableState` property instead of the [state](AnimationContext/state.zh-Hans.md) property:

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

The animation can also retrieve environment values of the view that created the animation. To retrieve a view’s environment value, use the context’s [environment](AnimationContext/environment.zh-Hans.md) property. For instance, the following code creates a custom [EnvironmentValues](EnvironmentValues.zh-Hans.md) property named `animationPaused`, and the view `PausableAnimationView` uses the property to store the paused state:

```swift
extension EnvironmentValues {
    @Entry var animationPaused: Bool = false
}

struct PausableAnimationView: View {
    @State private var paused = false

    var body: some View {
        VStack {
            ...
        }
        .environment(\.animationPaused, paused)
    }
}
```

Then the custom animation `PausableAnimation` retrieves the paused state from the view’s environment using the [environment](AnimationContext/environment.zh-Hans.md) property:

```swift
struct PausableAnimation: CustomAnimation {
    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        let paused = context.environment.animationPaused
        ...
    }
}
```

## Managing state

- **state**: The current state of a custom animation.

## Retrieving view environment values

- **environment**: The current environment of the view that created the custom animation.

## Creating context

- **withState(_:)**: Creates a new context from another one with a state that you provide.

## Instance Properties

- **isLogicallyComplete**: Set this to `true` to indicate that an animation is logically complete.

## Creating custom animations

- **CustomAnimation**: A type that defines how an animatable value changes over time.
- **AnimationState**: A container that stores the state for a custom animation.
- **AnimationStateKey**: A key for accessing animation state values.
- **UnitCurve**: A  function defined by a two-dimensional curve that maps an input progress in the range [0,1] to an output progress that is also in the range [0,1]. By changing the shape of the curve, the effective speed of an animation or other interpolation can be changed.
- **Spring**: A representation of a spring’s motion.

