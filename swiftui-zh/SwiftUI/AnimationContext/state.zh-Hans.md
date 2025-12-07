---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationContext/state
抓取时间： 2025-12-03T06:14:31Z
---

# 状态

**实例属性**

自定义动画的当前状态。

## 声明

```swift
var state: AnimationState<Value>
```

## 讨论

在动画运行时，[CustomAnimation](../CustomAnimation.zh-Hans.md) 的实例使用此属性读写状态值。

在自定义动画中使用`state` 属性的另一种方法是创建[AnimationStateKey](../AnimationStateKey.zh-Hans.md) 类型，并用自定义属性扩展[AnimationContext](../AnimationContext.zh-Hans.md)，以自定义类型返回状态。例如，下面的代码创建了一个名为`PausableState`的状态键。在键类型中存储状态值很方便，因此`PausableState` 结构包含了存储状态值 `paused` 和 `pauseTime` 的属性。

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

为了提供对可暂停状态的访问，以下代码扩展了 `AnimationContext` 以包含 `pausableState` 属性。该属性返回存储在[state](state.zh-Hans.md) 中的`PausableState` 结构的自定义`PausableState` 实例，它还可以在`state` 中存储一个新的`PausableState` 实例。

```swift
extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

现在，自定义动画可以使用`pausableState` 属性代替[state](state.zh-Hans.md) 属性，以便在动画运行时读写状态值。

```swift
struct PausableAnimation: CustomAnimation {
    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        let pausableState = context.pausableState
        var pauseTime = pausableState.pauseTime
        ...
    }
}
```属性


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationContext/state
crawled: 2025-12-03T06:14:31Z
---

# state

**Instance Property**

The current state of a custom animation.

## Declaration

```swift
var state: AnimationState<Value>
```

## Discussion

An instance of [CustomAnimation](../CustomAnimation.zh-Hans.md) uses this property to read and write state values as the animation runs.

An alternative to using the `state` property in a custom animation is to create an [AnimationStateKey](../AnimationStateKey.zh-Hans.md) type and extend [AnimationContext](../AnimationContext.zh-Hans.md) with a custom property that returns the state as a custom type. For example, the following code creates a state key named `PausableState`. It’s convenient to store state values in the key type, so the `PausableState` structure includes properties for the stored state values `paused` and `pauseTime`.

```swift
private struct PausableState<Value: VectorArithmetic>: AnimationStateKey {
    var paused = false
    var pauseTime: TimeInterval = 0.0

    static var defaultValue: Self { .init() }
}
```

To provide access to the pausable state, the following code extends `AnimationContext` to include the `pausableState` property. This property returns an instance of the custom `PausableState` structure stored in [state](state.zh-Hans.md), and it can also store a new `PausableState` instance in `state`.

```swift
extension AnimationContext {
    fileprivate var pausableState: PausableState<Value> {
        get { state[PausableState<Value>.self] }
        set { state[PausableState<Value>.self] = newValue }
    }
}
```

Now a custom animation can use the `pausableState` property instead of the [state](state.zh-Hans.md) property as a convenient way to read and write state values as the animation runs.

```swift
struct PausableAnimation: CustomAnimation {
    func animate<V>(value: V, time: TimeInterval, context: inout AnimationContext<V>) -> V? where V : VectorArithmetic {
        let pausableState = context.pausableState
        var pauseTime = pausableState.pauseTime
        ...
    }
}
```

