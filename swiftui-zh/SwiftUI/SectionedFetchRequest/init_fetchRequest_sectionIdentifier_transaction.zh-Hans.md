---
来源：https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(fetchRequest:sectionIdentifier:transaction:)
抓取时间：2025-11-30T22:32:49Z


# init(fetchRequest:sectionIdentifier:transaction:)

**Initializer**

创建完全配置的分段获取请求，更新结果时使用指定的事务。

### 声明

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, sectionIdentifier: KeyPath<Result, SectionIdentifier>, transaction: Transaction)
```

## 参数

- **fetchRequest**：一个 [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] 实例，用于描述从持久性存储中检索数据的搜索条件。
- **sectionIdentifier**：SwiftUI 应用于 `Result` 类型的键路径，用于获取对象的部分标识符。
- **transaction**：用于因获取的结果发生变化而导致用户界面变化的事务。

## 讨论

如果您需要基于[Transaction](../Transaction.zh-Hans.md) 的更新来获取影响用户界面的请求，请使用此初始化器。否则，请使用 [init(fetchRequest:sectionIdentifier:animation:)](init_fetchRequest_sectionIdentifier_animation.zh-Hans.md)。

## 创建完全配置的获取请求

- **init(fetchRequest:sectionIdentifier:animation:)**：创建一个完全配置的分段获取请求，在更新结果时使用指定的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(fetchRequest:sectionIdentifier:transaction:)
crawled: 2025-11-30T22:32:49Z
---

# init(fetchRequest:sectionIdentifier:transaction:)

**Initializer**

Creates a fully configured sectioned fetch request that uses the specified transaction when updating results.

## Declaration

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, sectionIdentifier: KeyPath<Result, SectionIdentifier>, transaction: Transaction)
```

## Parameters

- **fetchRequest**: An [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] instance that describes the search criteria for retrieving data from the persistent store.
- **sectionIdentifier**: A key path that SwiftUI applies to the `Result` type to get an object’s section identifier.
- **transaction**: A transaction to use for user interface changes that result from changes to the fetched results.

## Discussion

Use this initializer if you need a fetch request with updates that affect the user interface based on a [Transaction](../Transaction.zh-Hans.md). Otherwise, use [init(fetchRequest:sectionIdentifier:animation:)](init_fetchRequest_sectionIdentifier_animation.zh-Hans.md).

## Creating a fully configured fetch request

- **init(fetchRequest:sectionIdentifier:animation:)**: Creates a fully configured sectioned fetch request that uses the specified animation when updating results.

