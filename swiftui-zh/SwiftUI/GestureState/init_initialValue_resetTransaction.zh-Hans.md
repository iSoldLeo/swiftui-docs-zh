---
来源：https://developer.apple.com/documentation/SwiftUI/GestureState/init(initialValue:resetTransaction:)
抓取时间：2025-12-01T11:33:33Z
---

# init(initialValue:resetTransaction:)

**Initializer**

创建一个视图状态，该状态源于一个具有初始状态值的手势和一个用于重置初始状态值的事务。

### 声明

```swift
init(initialValue: Value, resetTransaction: Transaction)
```

## 参数

- **initialValue**：初始状态值。
- **resetTransaction**：为视图更新提供元数据的事务。

## 创建手势状态

- **init(initialValue:)**：创建一个视图状态，该视图状态源自一个具有初始值的手势。
- **init(initialValue:reset:)**：创建一个视图状态，该视图状态源于一个具有初始状态值的手势和一个提供重置事务的闭包。
- **init(reset:)**：创建一个视图状态，该视图状态源于一个手势和一个提供事务重置的闭包。
- **init(resetTransaction:)**：创建从手势派生的视图状态，并提供事务来重置它。
- **init(wrappedValue:)**：创建从手势派生的视图状态。
- **init(wrappedValue:reset:)**：创建从手势派生的视图状态，该视图状态具有一个封装状态值和一个闭包，闭包提供了一个重置状态值的事务。
- **init(wrappedValue:resetTransaction:)**：创建一个视图状态，该视图状态派生于一个具有包裹状态值的手势和一个重置它的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/GestureState/init(initialValue:resetTransaction:)
crawled: 2025-12-01T11:33:33Z
---

# init(initialValue:resetTransaction:)

**Initializer**

Creates a view state that’s derived from a gesture with an initial state value and a transaction to reset it.

## Declaration

```swift
init(initialValue: Value, resetTransaction: Transaction)
```

## Parameters

- **initialValue**: An initial state value.
- **resetTransaction**: A transaction that provides metadata for view updates.

## Creating a gesture state

- **init(initialValue:)**: Creates a view state that’s derived from a gesture with an initial value.
- **init(initialValue:reset:)**: Creates a view state that’s derived from a gesture with an initial state value and a closure that provides a transaction to reset it.
- **init(reset:)**: Creates a view state that’s derived from a gesture with a closure that provides a transaction to reset it.
- **init(resetTransaction:)**: Creates a view state that’s derived from a gesture with a transaction to reset it.
- **init(wrappedValue:)**: Creates a view state that’s derived from a gesture.
- **init(wrappedValue:reset:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a closure that provides a transaction to reset it.
- **init(wrappedValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a transaction to reset it.

