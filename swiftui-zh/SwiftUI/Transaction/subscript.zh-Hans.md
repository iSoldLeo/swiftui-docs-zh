---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/subscript(_:)
抓取时间： 2025-12-03T06:17:25Z
---

# 下标(_:)

**实例下标**

访问与自定义键相关的事务值。

## 声明

```swift
subscript<K>(key: K.Type) -> K.Value where K : TransactionKey { get set }
```

## 概览

通过定义一个符合[TransactionKey](../TransactionKey.zh-Hans.md) 协议的密钥来创建自定义事务值，然后使用该密钥和[Transaction](../Transaction.zh-Hans.md) 结构的下标操作符来获取和设置该密钥的值：

```swift
private struct MyTransactionKey: TransactionKey {
    static let defaultValue = false
}

extension Transaction {
    var myCustomValue: Bool {
        get { self[MyTransactionKey.self] }
        set { self[MyTransactionKey.self] = newValue }
    }
}
```

## 获取事务信息

- **isContinuous**：布尔值，表示事务是否源于产生一连串值的操作。
- **scrollTargetAnchor**：滚动到视图时，视图在滚动视图可见区域内的首选对齐方式。
- **tracksVelocity**：该事务是否会跟踪任何动画属性的变化速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/subscript(_:)
crawled: 2025-12-03T06:17:25Z
---

# subscript(_:)

**Instance Subscript**

Accesses the transaction value associated with a custom key.

## Declaration

```swift
subscript<K>(key: K.Type) -> K.Value where K : TransactionKey { get set }
```

## Overview

Create custom transaction values by defining a key that conforms to the [TransactionKey](../TransactionKey.zh-Hans.md) protocol, and then using that key with the subscript operator of the [Transaction](../Transaction.zh-Hans.md) structure to get and set a value for that key:

```swift
private struct MyTransactionKey: TransactionKey {
    static let defaultValue = false
}

extension Transaction {
    var myCustomValue: Bool {
        get { self[MyTransactionKey.self] }
        set { self[MyTransactionKey.self] = newValue }
    }
}
```

## Getting information about a transaction

- **isContinuous**: A Boolean value that indicates whether the transaction originated from an action that produces a sequence of values.
- **scrollTargetAnchor**: The preferred alignment of the view within a scroll view’s visible region when scrolling to a view.
- **tracksVelocity**: Whether this transaction will track the velocity of any animatable properties that change.

