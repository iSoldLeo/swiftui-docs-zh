---
来源： https://developer.apple.com/documentation/SwiftUI/Binding/transaction
抓取时间： 2025-12-03T06:06:45Z
---

# 交易

**实例属性**

绑定的事务。

## 声明

```swift
var transaction: Transaction
```

## 讨论

当绑定值发生变化时，事务会捕获更新视图所需的信息。

## 管理更改

- **id**：与此实例关联的实体的稳定标识，对应于绑定的包装值的`id`。
- **animation(_:)**：指定绑定值发生变化时要执行的动画。
- **transaction(_:)**：指定绑定的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/transaction
crawled: 2025-12-03T06:06:45Z
---

# transaction

**Instance Property**

The binding’s transaction.

## Declaration

```swift
var transaction: Transaction
```

## Discussion

The transaction captures the information needed to update the view when the binding value changes.

## Managing changes

- **id**: The stable identity of the entity associated with this instance, corresponding to the `id` of the binding’s wrapped value.
- **animation(_:)**: Specifies an animation to perform when the binding value changes.
- **transaction(_:)**: Specifies a transaction for the binding.

