--- 来源：https://developer.apple.com/documentation/SwiftUI/AnimationStateKey

抓取时间：2025-12-02T17:34:01Z

---

# AnimationStateKey

**Protocol**

用于访问动画状态值的键。

## 声明

```swift
protocol AnimationStateKey
```

## 概述

要在自定义动画中访问 [AnimationContext](AnimationContext.zh-Hans.md) 的动画状态，请创建一个 `AnimationStateKey`。例如，以下代码创建了一个名为 `PausableState` 的动画状态键，并设置了所需的 [defaultValue](AnimationStateKey/defaultValue.zh-Hans.md) 属性的值。该代码还定义了自定义动画在计算动画值时所需的状态值属性。将状态值保存在动画状态键中，可以更方便地在 [CustomAnimation](CustomAnimation.zh-Hans.md) 的实现中读取和写入这些值。

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

为了更方便地访问动画状态键的值，请通过扩展 [AnimationContext](AnimationContext.zh-Hans.md) 为其定义一个属性：

```swift
extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

然后，您可以使用 [AnimationContext](AnimationContext.zh-Hans.md) 在 `CustomAnimation` 的实例中读取和写入状态：

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

## 设置默认值

- **defaultValue**：动画状态键的默认值。

- **Value**：表示动画状态键值类型的关联类型。

## 创建自定义动画

- **CustomAnimation**：定义可动画值随时间变化方式的类型。

- **AnimationContext**：自定义动画可用于管理状态和访问视图环境的上下文值。

- **AnimationState**：存储自定义动画状态的容器。

- **UnitCurve**：由二维曲线定义的函数，该曲线将 [0,1] 范围内的输入进度映射到同样在 [0,1] 范围内的输出进度。通过改变曲线的形状，可以改变动画或其他插值的有效速度。

- **Spring**：弹簧运动的表示。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationStateKey
crawled: 2025-12-02T17:34:01Z
---

# AnimationStateKey

**Protocol**

A key for accessing animation state values.

## Declaration

```swift
protocol AnimationStateKey
```

## Overview

To access animation state from an [AnimationContext](AnimationContext.zh-Hans.md) in a custom animation, create an `AnimationStateKey`. For example, the following code creates an animation state key named `PausableState` and sets the value for the required [defaultValue](AnimationStateKey/defaultValue.zh-Hans.md) property. The code also defines properties for state values that the custom animation needs when calculating animation values. Keeping the state values in the animation state key makes it more convenient to read and write those values in the implementation of a [CustomAnimation](CustomAnimation.zh-Hans.md).

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

To make accessing the value of the animation state key more convenient, define a property for it by extending [AnimationContext](AnimationContext.zh-Hans.md):

```swift
extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

Then, you can read and write your state in an instance of `CustomAnimation` using the [AnimationContext](AnimationContext.zh-Hans.md):

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

## Setting the default value

- **defaultValue**: The default value for the animation state key.
- **Value**: The associated type representing the type of the animation state key’s value.

## Creating custom animations

- **CustomAnimation**: A type that defines how an animatable value changes over time.
- **AnimationContext**: Contextual values that a custom animation can use to manage state and access a view’s environment.
- **AnimationState**: A container that stores the state for a custom animation.
- **UnitCurve**: A  function defined by a two-dimensional curve that maps an input progress in the range [0,1] to an output progress that is also in the range [0,1]. By changing the shape of the curve, the effective speed of an animation or other interpolation can be changed.
- **Spring**: A representation of a spring’s motion.

