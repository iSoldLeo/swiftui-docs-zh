---

来源：https://developer.apple.com/documentation/SwiftUI/View/transaction(_:body:)

抓取时间：2025-11-30T21:19:40Z

---

# transaction(_:body:)

**实例方法**

将给定的事务变更函数应用于 `body` 闭包中使用的所有动画。

## 声明

```swift
nonisolated func transaction<V>(_ transform: @escaping (inout Transaction) -> Void, @ViewBuilder body: (PlaceholderContentView<Self>) -> V) -> some View where V : View

```

## 说明

应用于 `body` 内容的任何修饰符都将应用于此视图，而对 `transform` 中执行的事务所做的更改只会影响 `body` 中定义的修饰符。

以下代码使用更快的动画效果来改变不透明度，同时 MyView 的内容使用隐式事务进行动画处理：

```swift
MyView(isActive: isActive)
    .transaction { transaction in
        transaction.animation = transaction.animation?.speed(2)
    } body: { content in
        content.opacity(isActive ? 1.0 : 0.0)
    }
```

- 另请参阅：`Transaction.disablesAnimations`

## 将动画移动到另一个视图

- **withTransaction(_:_:)**：使用指定的事务执行闭包并返回结果。

- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包并返回结果。

- **transaction(_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **transaction(value:_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **Transaction**：当前状态处理更新的上下文。

- **Entry()**：创建环境值、事务值、容器值或焦点值条目。

- **TransactionKey**：用于访问事务中值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transaction(_:body:)
crawled: 2025-11-30T21:19:40Z
---

# transaction(_:body:)

**Instance Method**

Applies the given transaction mutation function to all animations used within the `body` closure.

## Declaration

```swift
nonisolated func transaction<V>(_ transform: @escaping (inout Transaction) -> Void, @ViewBuilder body: (PlaceholderContentView<Self>) -> V) -> some View where V : View

```

## Discussion

Any modifiers applied to the content of `body` will be applied to this view, and the changes to the transaction performed in the `transform` will only affect the modifiers defined in the `body`.

The following code animates the opacity changing with a faster animation, while the contents of MyView are animated with the implicit transaction:

```swift
MyView(isActive: isActive)
    .transaction { transaction in
        transaction.animation = transaction.animation?.speed(2)
    } body: { content in
        content.opacity(isActive ? 1.0 : 0.0)
    }
```

- See Also: `Transaction.disablesAnimations`

## Moving an animation to another view

- **withTransaction(_:_:)**: Executes a closure with the specified transaction and returns the result.
- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **Transaction**: The context of the current state-processing update.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **TransactionKey**: A key for accessing values in a transaction.

