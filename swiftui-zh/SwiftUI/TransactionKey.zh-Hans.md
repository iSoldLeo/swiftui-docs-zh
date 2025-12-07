---
来源： https://developer.apple.com/documentation/SwiftUI/TransactionKey
抓取时间： 2025-12-02T17:34:34Z
---

# 交易密钥

**Protocol**

用于访问事务中的值的键。

## 声明

```swift
protocol TransactionKey
```

## 概览

通过使用新属性扩展[Transaction](Transaction.zh-Hans.md) 结构，可以创建自定义事务值。首先声明一个新的事务键类型，并为所需的[defaultValue](TransactionKey/defaultValue.zh-Hans.md) 属性指定一个值：

```swift
private struct MyTransactionKey: TransactionKey {
    static let defaultValue = false
}
```

Swift 编译器会自动将关联的 [Value](TransactionKey/Value.zh-Hans.md) 类型推断为您为默认值指定的类型。然后使用该键定义新的事务值属性：

```swift
extension Transaction {
    var myCustomValue: Bool {
        get { self[MyTransactionKey.self] }
        set { self[MyTransactionKey.self] = newValue }
    }
}
```

事务值的客户端不会直接使用键。相反，它们会使用自定义事务值属性的键路径。要为某个更改设置事务值，请在调用`withTransaction` 时封装该更改：

```swift
withTransaction(\.myCustomValue, true) {
    isActive.toggle()
}
```

要使用`MyView` 或其后代中的值，请使用 [transaction(_:)](View/transaction.zh-Hans.md) 视图修饰符：

```swift
MyView()
    .transaction { transaction in
        if transaction.myCustomValue {
            transaction.animation = .default.repeatCount(3)
        }
    }
```

## 设置默认值

- **defaultValue**：事务键的默认值。
- **Value**：表示事务键值类型的关联类型。

## 将动画移动到另一个视图

- **withTransaction(_:_:)**：使用指定的事务执行闭包并返回结果。
- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包并返回结果。
- **transaction(_:)**：将给定的事务突变函数应用到视图中使用的所有动画。
- **transaction(value:_:)**：将给定的事务突变函数应用到视图中使用的所有动画。
- **transaction(_:body:)**：将给定的事务突变函数应用于在`body` 闭包中使用的所有动画。
- **Transaction**：当前状态处理更新的上下文。
- **Entry()**：当前状态处理更新的上下文：创建环境值、事务、容器值或集中值条目。


---
source: https://developer.apple.com/documentation/SwiftUI/TransactionKey
crawled: 2025-12-02T17:34:34Z
---

# TransactionKey

**Protocol**

A key for accessing values in a transaction.

## Declaration

```swift
protocol TransactionKey
```

## Overview

You can create custom transaction values by extending the [Transaction](Transaction.zh-Hans.md) structure with new properties. First declare a new transaction key type and specify a value for the required [defaultValue](TransactionKey/defaultValue.zh-Hans.md) property:

```swift
private struct MyTransactionKey: TransactionKey {
    static let defaultValue = false
}
```

The Swift compiler automatically infers the associated [Value](TransactionKey/Value.zh-Hans.md) type as the type you specify for the default value. Then use the key to define a new transaction value property:

```swift
extension Transaction {
    var myCustomValue: Bool {
        get { self[MyTransactionKey.self] }
        set { self[MyTransactionKey.self] = newValue }
    }
}
```

Clients of your transaction value never use the key directly. Instead, they use the key path of your custom transaction value property. To set the transaction value for a change, wrap that change in a call to `withTransaction`:

```swift
withTransaction(\.myCustomValue, true) {
    isActive.toggle()
}
```

To use the value from inside `MyView` or one of its descendants, use the [transaction(_:)](View/transaction.zh-Hans.md) view modifier:

```swift
MyView()
    .transaction { transaction in
        if transaction.myCustomValue {
            transaction.animation = .default.repeatCount(3)
        }
    }
```

## Setting a default value

- **defaultValue**: The default value for the transaction key.
- **Value**: The associated type representing the type of the transaction key’s value.

## Moving an animation to another view

- **withTransaction(_:_:)**: Executes a closure with the specified transaction and returns the result.
- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **Transaction**: The context of the current state-processing update.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.

