---
来源：https://developer.apple.com/documentation/SwiftUI/GestureState/init(initialValue:)
抓取时间： 2025-12-01T11:33:31Z
---

# init(initialValue:)

**Initializer**

创建一个视图状态，该状态源于一个带有初始值的手势。

## 声明

```swift
init(initialValue: Value)
```

## 参数

- **initialValue**：手势状态属性的初始值。

## 创建手势状态

- **init(initialValue:reset:)**：创建一个视图状态，该状态源于一个手势，并带有初始状态值和一个提供重置事务的闭包。
- **init(initialValue:resetTransaction:)**：创建一个视图状态，该视图状态源于一个具有初始状态值的手势和一个用于重置它的事务。
- **init(reset:)**：创建一个视图状态，该视图状态从手势派生，并带有一个提供事务重置的闭包。
- **init(resetTransaction:)**：创建从手势派生的视图状态，并提供事务来重置它。
- **init(wrappedValue:)**：创建从手势派生的视图状态。
- **init(wrappedValue:reset:)**：创建从手势派生的视图状态，该视图状态具有一个封装状态值和一个闭包，闭包提供了一个重置状态值的事务。
- **init(wrappedValue:resetTransaction:)**：创建一个视图状态，该视图状态派生于一个具有包裹状态值的手势和一个重置它的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/GestureState/init(initialValue:)
crawled: 2025-12-01T11:33:31Z
---

# init(initialValue:)

**Initializer**

Creates a view state that’s derived from a gesture with an initial value.

## Declaration

```swift
init(initialValue: Value)
```

## Parameters

- **initialValue**: An initial value for the gesture state property.

## Creating a gesture state

- **init(initialValue:reset:)**: Creates a view state that’s derived from a gesture with an initial state value and a closure that provides a transaction to reset it.
- **init(initialValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with an initial state value and a transaction to reset it.
- **init(reset:)**: Creates a view state that’s derived from a gesture with a closure that provides a transaction to reset it.
- **init(resetTransaction:)**: Creates a view state that’s derived from a gesture with a transaction to reset it.
- **init(wrappedValue:)**: Creates a view state that’s derived from a gesture.
- **init(wrappedValue:reset:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a closure that provides a transaction to reset it.
- **init(wrappedValue:resetTransaction:)**: Creates a view state that’s derived from a gesture with a wrapped state value and a transaction to reset it.

