---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationContext/withState(_:)
抓取时间： 2025-12-03T06:14:33Z
---

# withState(_:)

**实例方法**

根据您提供的状态从另一个上下文创建一个新的上下文。

## 声明

```swift
func withState<T>(_ state: AnimationState<T>) -> AnimationContext<T> where T : VectorArithmetic
```

## 参数

- **state**：新上下文的初始状态。

## 返回值

包含指定状态的新上下文。

## 讨论

使用此方法可创建一个包含您提供的状态的新上下文，并查看原始上下文中的环境值。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationContext/withState(_:)
crawled: 2025-12-03T06:14:33Z
---

# withState(_:)

**Instance Method**

Creates a new context from another one with a state that you provide.

## Declaration

```swift
func withState<T>(_ state: AnimationState<T>) -> AnimationContext<T> where T : VectorArithmetic
```

## Parameters

- **state**: The initial state for the new context.

## Return Value

A new context that contains the specified state.

## Discussion

Use this method to create a new context that contains the state that you provide and view environment values from the original context.

