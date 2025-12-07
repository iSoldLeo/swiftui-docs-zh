--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/onEnded(_:)

抓取时间：2025-12-01T11:33:22Z

---

# onEnded(_:)

**实例方法**

添加手势结束时要执行的操作。

## 声明

```swift
nonisolated func onEnded(_ action: @escaping (Self.Value) -> Void) -> _EndedGesture<Self>
```

## 参数

- **action**：手势结束时要执行的操作。`action` 闭包的参数包含手势的最终值。

## 返回值

一个手势，当手势结束时触发 `action`。

## 讨论

## 执行手势

- **updating(_:body:)**：当手势值发生变化时，更新提供的手势状态属性。

- **onChanged(_:)**：添加一个在手势值发生变化时要执行的操作。

- **Value**：表示手势值的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/onEnded(_:)
crawled: 2025-12-01T11:33:22Z
---

# onEnded(_:)

**Instance Method**

Adds an action to perform when the gesture ends.

## Declaration

```swift
nonisolated func onEnded(_ action: @escaping (Self.Value) -> Void) -> _EndedGesture<Self>
```

## Parameters

- **action**: The action to perform when this gesture ends. The `action` closure’s parameter contains the final value of the gesture.

## Return Value

A gesture that triggers `action` when the gesture ends.

## Discussion



## Performing the gesture

- **updating(_:body:)**: Updates the provided gesture state property as the gesture’s value changes.
- **onChanged(_:)**: Adds an action to perform when the gesture’s value changes.
- **Value**: The type representing the gesture’s value.

