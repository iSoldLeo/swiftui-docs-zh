--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(fetchRequest:transaction:)

抓取时间：2025-11-30T22:32:33Z

---

# init(fetchRequest:transaction:)

**Initializer**

创建一个完全配置的 fetch 请求，该请求在更新结果时使用指定的事务。

## 声明

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, transaction: Transaction)
```

## 参数

- **fetchRequest**：一个 [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] 实例，用于描述从持久化存储中检索数据的搜索条件。

- **transaction**：用于处理因获取结果的更改而导致的用户界面更改的事务。

## 讨论

如果您需要基于 [Transaction](../Transaction.zh-Hans.md) 更新用户界面，请使用此初始化程序。否则，请使用 [init(fetchRequest:animation:)](init_fetchRequest_animation.zh-Hans.md)。

## 创建完全配置的获取请求

- **init(fetchRequest:animation:)**：创建一个完全配置的获取请求，该请求在更新结果时使用指定的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(fetchRequest:transaction:)
crawled: 2025-11-30T22:32:33Z
---

# init(fetchRequest:transaction:)

**Initializer**

Creates a fully configured fetch request that uses the specified transaction when updating results.

## Declaration

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, transaction: Transaction)
```

## Parameters

- **fetchRequest**: An [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] instance that describes the search criteria for retrieving data from the persistent store.
- **transaction**: A transaction to use for user interface changes that result from changes to the fetched results.

## Discussion

Use this initializer if you need a fetch request with updates that affect the user interface based on a [Transaction](../Transaction.zh-Hans.md). Otherwise, use [init(fetchRequest:animation:)](init_fetchRequest_animation.zh-Hans.md).

## Creating a fully configured fetch request

- **init(fetchRequest:animation:)**: Creates a fully configured fetch request that uses the specified animation when updating results.

