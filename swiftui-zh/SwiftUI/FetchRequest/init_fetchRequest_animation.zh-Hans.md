--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(fetchRequest:animation:)

抓取时间：2025-12-02T18:48:09Z
---

# init(fetchRequest:animation:)

**Initializer**

创建一个配置完整的 fetch 请求，该请求在更新结果时使用指定的动画。

## 声明

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, animation: Animation? = nil)
```

## 参数

- **fetchRequest**：一个 [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] 实例，用于描述从持久存储中检索数据的搜索条件。

- **animation**：用于响应已获取结果更改的用户界面更改的动画。

## 讨论

当您想要配置一个包含谓词和排序描述符之外的其他信息的获取请求时，请使用此初始化器。例如，您可以从一个托管对象（`Quake`）发出请求，该对象由示例代码项目定义，用于存储地震数据。通过为请求设置一个属性（[doc://com.apple.documentation/documentation/CoreData/NSFetchRequest/fetchLimit]），将结果数量限制为 `1000`：

```swift
extension Quake {
    var request: NSFetchRequest<Quake> {
        let request = NSFetchRequest<Quake>(entityName: "Quake")
        request.sortDescriptors = [
            NSSortDescriptor(
                keyPath: \Quake.time,
                ascending: true)]
        request.fetchLimit = 1000
        return request
    }
}
```

使用此请求定义一个属性（[FetchedResults](../FetchedResults.zh-Hans.md)）：

```swift
@FetchRequest(fetchRequest: Quake.request)
private var quakes: FetchedResults<Quake>
```

如果您只需要配置请求的谓词和排序描述符，请改用 [init(sortDescriptors:predicate:animation:)](init_sortDescriptors_predicate_animation.zh-Hans.md)。如果需要指定 [Transaction](../Transaction.zh-Hans.md) 而不是可选的 [Animation](../Animation.zh-Hans.md)，请使用 [init(fetchRequest:transaction:)](init_fetchRequest_transaction.zh-Hans.md)。

## 创建完全配置的获取请求

- **init(fetchRequest:transaction:)**：创建一个完全配置的获取请求，该请求在更新结果时使用指定的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(fetchRequest:animation:)
crawled: 2025-12-02T18:48:09Z
---

# init(fetchRequest:animation:)

**Initializer**

Creates a fully configured fetch request that uses the specified animation when updating results.

## Declaration

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, animation: Animation? = nil)
```

## Parameters

- **fetchRequest**: An [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] instance that describes the search criteria for retrieving data from the persistent store.
- **animation**: The animation to use for user interface changes that result from changes to the fetched results.

## Discussion

Use this initializer when you want to configure a fetch request with more than a predicate and sort descriptors. For example, you can vend a request from a `Quake` managed object that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines to store earthquake data. Limit the number of results to `1000` by setting a [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest/fetchLimit] for the request:

```swift
extension Quake {
    var request: NSFetchRequest<Quake> {
        let request = NSFetchRequest<Quake>(entityName: "Quake")
        request.sortDescriptors = [
            NSSortDescriptor(
                keyPath: \Quake.time,
                ascending: true)]
        request.fetchLimit = 1000
        return request
    }
}
```

Use the request to define a [FetchedResults](../FetchedResults.zh-Hans.md) property:

```swift
@FetchRequest(fetchRequest: Quake.request)
private var quakes: FetchedResults<Quake>
```

If you only need to configure the request’s predicate and sort descriptors, use [init(sortDescriptors:predicate:animation:)](init_sortDescriptors_predicate_animation.zh-Hans.md) instead. If you need to specify a [Transaction](../Transaction.zh-Hans.md) rather than an optional [Animation](../Animation.zh-Hans.md), use [init(fetchRequest:transaction:)](init_fetchRequest_transaction.zh-Hans.md).

## Creating a fully configured fetch request

- **init(fetchRequest:transaction:)**: Creates a fully configured fetch request that uses the specified transaction when updating results.

