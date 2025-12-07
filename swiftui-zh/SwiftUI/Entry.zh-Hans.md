---
来源： https://developer.apple.com/documentation/SwiftUI/Entry()
抓取时间： 2025-12-02T17:32:22Z
---

# Entry()

**Macro**

创建环境值、事务、容器值或集中值条目。

## 声明

```swift
@attached(accessor) @attached(peer, names: prefixed(__Key_)) macro Entry()
```

## 环境值

使用新属性扩展[EnvironmentValues](EnvironmentValues.zh-Hans.md) 结构，并在变量声明中附加 @Entry 宏，从而创建⟦条目：

```swift
extension EnvironmentValues {
    @Entry var myCustomValue: String = "Default value"
    @Entry var anotherCustomValue = true
}
```

## 交易值

使用新属性扩展[Transaction](Transaction.zh-Hans.md) 结构并在变量声明中附加 @Entry 宏，从而创建⟦条目：

```swift
extension Transaction {
    @Entry var myCustomValue: String = "Default value"
}
```

## 容器值

使用新属性扩展[ContainerValues](ContainerValues.zh-Hans.md) 结构并在变量声明中附加 @Entry 宏，从而创建⟦条目：

```swift
extension ContainerValues {
    @Entry var myCustomValue: String = "Default value"
}
```

## 重点值

由于 [FocusedValues](FocusedValues.zh-Hans.md) 的缺省值始终是 `nil`，因此 [FocusedValues](FocusedValues.zh-Hans.md) 条目不能指定不同的缺省值，而且必须是可选类型。

通过使用新属性扩展[FocusedValues](FocusedValues.zh-Hans.md) 结构并在变量声明中附加 @Entry 宏，创建[FocusedValues](FocusedValues.zh-Hans.md) 条目：

```swift
extension FocusedValues {
    @Entry var myCustomValue: String?
}
```

## 将动画移动到另一个视图中

- **withTransaction(_:_:)**：使用指定的事务执行闭包并返回结果。
- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包，并返回结果。
- **transaction(_:)**：将给定的事务突变函数应用到视图中使用的所有动画。
- **transaction(value:_:)**：将给定的事务突变函数应用到视图中使用的所有动画。
- **transaction(_:body:)**：将给定的事务突变函数应用于在`body` 闭包中使用的所有动画。
- **Transaction**：当前状态处理更新的上下文。
- **TransactionKey**：当前状态处理更新的上下文：用于访问事务中值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/Entry()
crawled: 2025-12-02T17:32:22Z
---

# Entry()

**Macro**

Creates an environment values, transaction, container values, or focused values entry.

## Declaration

```swift
@attached(accessor) @attached(peer, names: prefixed(__Key_)) macro Entry()
```

## Environment Values

Create [EnvironmentValues](EnvironmentValues.zh-Hans.md) entries by extending the [EnvironmentValues](EnvironmentValues.zh-Hans.md) structure with new properties and attaching the @Entry macro to the variable declarations:

```swift
extension EnvironmentValues {
    @Entry var myCustomValue: String = "Default value"
    @Entry var anotherCustomValue = true
}
```

## Transaction Values

Create [Transaction](Transaction.zh-Hans.md) entries by extending the [Transaction](Transaction.zh-Hans.md) structure with new properties and attaching the @Entry macro to the variable declarations:

```swift
extension Transaction {
    @Entry var myCustomValue: String = "Default value"
}
```

## Container Values

Create [ContainerValues](ContainerValues.zh-Hans.md) entries by extending the [ContainerValues](ContainerValues.zh-Hans.md) structure with new properties and attaching the @Entry macro to the variable declarations:

```swift
extension ContainerValues {
    @Entry var myCustomValue: String = "Default value"
}
```

## Focused Values

Since the default value for [FocusedValues](FocusedValues.zh-Hans.md) is always `nil`, [FocusedValues](FocusedValues.zh-Hans.md) entries cannot specify a different default value and must have an Optional type.

Create [FocusedValues](FocusedValues.zh-Hans.md) entries by extending the [FocusedValues](FocusedValues.zh-Hans.md) structure with new properties and attaching the @Entry macro to the variable declarations:

```swift
extension FocusedValues {
    @Entry var myCustomValue: String?
}
```

## Moving an animation to another view

- **withTransaction(_:_:)**: Executes a closure with the specified transaction and returns the result.
- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **Transaction**: The context of the current state-processing update.
- **TransactionKey**: A key for accessing values in a transaction.

