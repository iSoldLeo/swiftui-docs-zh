--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/updating(_:body:)

抓取时间：2025-12-01T11:33:20Z

---

# updated(_:body:)

**实例方法**

当手势值发生变化时，更新提供的手势状态属性。

## 声明

```swift
@MainActor @preconcurrency func updating<State>(_ state: GestureState<State>, body: @escaping (Self.Value, inout State, inout Transaction) -> Void) -> GestureStateGesture<Self, State>
```

## 参数

- **state**：绑定到视图的 [GestureState](../GestureState.zh-Hans.md) 属性。

- **body**：SwiftUI 在手势值发生变化时调用的回调函数。其 `currentState` 参数是手势的更新状态。 `gestureState` 参数表示手势的先前状态，`transaction` 参数表示手势的上下文。

## 返回值

此手势版本会在原始手势的值发生变化时更新提供的 `state` 参数，并在用户或系统结束或取消手势时将 `state` 参数重置为其初始值。

## 说明

使用此回调函数更新瞬态 UI 状态，如 [Adding-Interactivity-with-Gestures](../Adding-Interactivity-with-Gestures.zh-Hans.md) 中所述。

## 执行手势

- **onChanged(_:)**：添加一个在手势值发生变化时要执行的操作。

- **onEnded(_:)**：添加一个在手势结束时要执行的操作。

- **Value**：表示手势值的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/updating(_:body:)
crawled: 2025-12-01T11:33:20Z
---

# updating(_:body:)

**Instance Method**

Updates the provided gesture state property as the gesture’s value changes.

## Declaration

```swift
@MainActor @preconcurrency func updating<State>(_ state: GestureState<State>, body: @escaping (Self.Value, inout State, inout Transaction) -> Void) -> GestureStateGesture<Self, State>
```

## Parameters

- **state**: A binding to a view’s [GestureState](../GestureState.zh-Hans.md) property.
- **body**: The callback that SwiftUI invokes as the gesture’s value changes. Its `currentState` parameter is the updated state of the gesture. The `gestureState` parameter is the previous state of the gesture, and the `transaction` is the context of the gesture.

## Return Value

A version of the gesture that updates the provided `state` as the originating gesture’s value changes and that resets the `state` to its initial value when the user or the system ends or cancels the gesture.

## Discussion

Use this callback to update transient UI state as described in [Adding-Interactivity-with-Gestures](../Adding-Interactivity-with-Gestures.zh-Hans.md).

## Performing the gesture

- **onChanged(_:)**: Adds an action to perform when the gesture’s value changes.
- **onEnded(_:)**: Adds an action to perform when the gesture ends.
- **Value**: The type representing the gesture’s value.

