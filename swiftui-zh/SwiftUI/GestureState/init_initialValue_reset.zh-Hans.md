---
来源：https://developer.apple.com/documentation/SwiftUI/GestureState/init(initialValue:reset:)
抓取时间：2025-12-03T06:44:15Z
---

# init(initialValue:reset:)

**Initializer**

创建一个视图状态，该状态源于一个具有初始状态值的手势和一个提供重置状态的事务的闭包。

### 声明

```swift
init(initialValue: Value, reset: @escaping (Value, inout Transaction) -> Void)
```

## 参数

- **initialValue**：初始状态值。
- **reset**：提供[Transaction](../Transaction.zh-Hans.md)的闭包。

## 创建手势状态

- **init(initialValue:)**：创建一个视图状态，该状态由带有初始值的手势衍生而来。
- **init(initialValue:resetTransaction:)**：创建从手势派生的视图状态，该视图状态具有初始状态值和重置它的事务。
- **init(reset:)**：创建一个视图状态，该视图状态从手势派生，并带有一个提供事务重置的闭包。
- **init(resetTransaction:)**：创建从手势派生的视图状态，并提供事务来重置它。
- **init(wrappedValue:)**：创建从手势派生的视图状态。
- **init(wrappedValue:reset:)**：创建从手势派生的视图状态，该视图状态具有一个封装状态值和一个闭包，闭包提供了一个重置状态值的事务。
- **init(wrappedValue:resetTransaction:)**：创建一个视图状态，该视图状态派生于一个具有包裹状态值的手势和一个重置它的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/GestureState/init(initialValue:reset:)
crawled: 2025-12-03T06:44:15Z
---

# init(initialValue:reset:)

**Initializer**

Creates a view state that’s derived from a gesture with an initial state value and a closure that provides a transaction to reset it.

## Declaration

```swift
init(initialValue: Value, reset: @escaping (Value, inout Transaction) -> Void)
```

## Parameters

- **initialValue**: An initial state value.
- **reset**: A closure that provides a [Transaction](../Transaction.zh-Hans.md).

## Creating a gesture state

- **init(initialValue:)**: Creates a view state that’s derived from a gesture with an initial value.
- **init(initialValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with an initial state value and a transaction to reset it.
- **init(reset:)**: Creates a view state that’s derived from a gesture with a closure that provides a transaction to reset it.
- **init(resetTransaction:)**: Creates a view state that’s derived from a gesture with a transaction to reset it.
- **init(wrappedValue:)**: Creates a view state that’s derived from a gesture.
- **init(wrappedValue:reset:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a closure that provides a transaction to reset it.
- **init(wrappedValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a transaction to reset it.

