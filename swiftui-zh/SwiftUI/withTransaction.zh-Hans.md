---
来源： https://developer.apple.com/documentation/SwiftUI/withTransaction(_:_:)
抓取时间： 2025-12-02T17:34:29Z
---

# withTransaction(_:_:)

**Function**

使用指定的事务执行闭包并返回结果。

## 声明

```swift
func withTransaction<Result>(_ transaction: Transaction, _ body: () throws -> Result) rethrows -> Result
```

## 参数

- **body**：要执行的闭包。

## 返回值

使用指定事务执行闭包的结果。

## 移动动画到另一个视图

- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包并返回结果。
- **transaction(_:)**：将给定的事务突变函数应用到视图中使用的所有动画。
- **transaction(value:_:)**：将给定的事务突变函数应用到视图中使用的所有动画。
- **transaction(_:body:)**：将给定的事务突变函数应用于在`body` 闭包中使用的所有动画。
- **Transaction**：当前状态处理更新的上下文。
- **Entry()**：当前状态处理更新的上下文：创建环境值、事务、容器值或集中值条目。
- **TransactionKey**：用于在事务中访问值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/withTransaction(_:_:)
crawled: 2025-12-02T17:34:29Z
---

# withTransaction(_:_:)

**Function**

Executes a closure with the specified transaction and returns the result.

## Declaration

```swift
func withTransaction<Result>(_ transaction: Transaction, _ body: () throws -> Result) rethrows -> Result
```

## Parameters

- **body**: A closure to execute.

## Return Value

The result of executing the closure with the specified transaction.

## Moving an animation to another view

- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **Transaction**: The context of the current state-processing update.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **TransactionKey**: A key for accessing values in a transaction.

