---
来源：https://developer.apple.com/documentation/SwiftUI/GestureState/init(wrappedValue:reset:)
抓取时间：2025-12-03T06:44:19Z
---

# init(wrappedValue:reset:)

**Initializer**

创建一个视图状态，该状态源于一个具有包裹状态值的手势和一个提供重置状态值的事务的闭包。

### 声明

```swift
init(wrappedValue: Value, reset: @escaping (Value, inout Transaction) -> Void)
```

## 参数

- **wrappedValue**：手势状态属性的包装值。
- **reset**：提供[Transaction](../Transaction.zh-Hans.md)的闭包。

## 创建手势状态

- **init(initialValue:)**：创建一个视图状态，该状态由带有初始值的手势衍生而来。
- **init(initialValue:reset:)**：创建一个视图状态，该视图状态源于一个具有初始状态值的手势和一个提供重置事务的闭包。
- **init(initialValue:resetTransaction:)**：创建一个视图状态，该视图状态源于一个具有初始状态值的手势和一个用于重置它的事务。
- **init(reset:)**：创建一个视图状态，该视图状态从手势派生，并带有一个提供事务重置的闭包。
- **init(resetTransaction:)**：创建从手势派生的视图状态，并提供事务来重置它。
- **init(wrappedValue:)**：创建从手势派生的视图状态。
- **init(wrappedValue:resetTransaction:)**：创建一个从手势派生的视图状态，该视图状态带有一个封装状态值和一个重置状态值的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/GestureState/init(wrappedValue:reset:)
crawled: 2025-12-03T06:44:19Z
---

# init(wrappedValue:reset:)

**Initializer**

Creates a view state that’s derived from a gesture with a wrapped state value and a closure that provides a transaction to reset it.

## Declaration

```swift
init(wrappedValue: Value, reset: @escaping (Value, inout Transaction) -> Void)
```

## Parameters

- **wrappedValue**: A wrapped value for the gesture state property.
- **reset**: A closure that provides a [Transaction](../Transaction.zh-Hans.md).

## Creating a gesture state

- **init(initialValue:)**: Creates a view state that’s derived from a gesture with an initial value.
- **init(initialValue:reset:)**: Creates a view state that’s derived from a gesture with an initial state value and a closure that provides a transaction to reset it.
- **init(initialValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with an initial state value and a transaction to reset it.
- **init(reset:)**: Creates a view state that’s derived from a gesture with a closure that provides a transaction to reset it.
- **init(resetTransaction:)**: Creates a view state that’s derived from a gesture with a transaction to reset it.
- **init(wrappedValue:)**: Creates a view state that’s derived from a gesture.
- **init(wrappedValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a transaction to reset it.

