--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/onChanged(_:)

抓取时间：2025-12-03T06:44:04Z

---

# onChanged(_:)

**实例方法**

添加一个在手势值改变时要执行的操作。

## 声明

```swift
@MainActor @preconcurrency func onChanged(_ action: @escaping (Self.Value) -> Void) -> _ChangedGesture<Self>
```

## 参数

- **action**：当此手势值改变时要执行的操作。`action` 闭包的参数包含手势的新值。

## 返回值

一个当此手势值改变时触发 `action` 的手势。

## 执行手势

- **updating(_:body:)**：根据手势值的变化更新提供的手势状态属性。

- **onEnded(_:)**：添加手势结束时要执行的操作。

- **Value**：表示手势值的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/onChanged(_:)
crawled: 2025-12-03T06:44:04Z
---

# onChanged(_:)

**Instance Method**

Adds an action to perform when the gesture’s value changes.

## Declaration

```swift
@MainActor @preconcurrency func onChanged(_ action: @escaping (Self.Value) -> Void) -> _ChangedGesture<Self>
```

## Parameters

- **action**: The action to perform when this gesture’s value changes. The `action` closure’s parameter contains the gesture’s new value.

## Return Value

A gesture that triggers `action` when this gesture’s value changes.

## Performing the gesture

- **updating(_:body:)**: Updates the provided gesture state property as the gesture’s value changes.
- **onEnded(_:)**: Adds an action to perform when the gesture ends.
- **Value**: The type representing the gesture’s value.

