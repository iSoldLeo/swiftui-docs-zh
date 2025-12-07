---
来源：https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(fetchRequest:sectionIdentifier:animation:)
抓取时间：2025-12-02T18:48:26Z
---

# init(fetchRequest:sectionIdentifier:animation:)

**Initializer**

创建一个已完全配置的分段获取请求，在更新结果时使用指定的动画。

### 声明

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, sectionIdentifier: KeyPath<Result, SectionIdentifier>, animation: Animation? = nil)
```

## 参数

- **fetchRequest**：一个 [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] 实例，用于描述从持久性存储中检索数据的搜索条件。
- **sectionIdentifier**：SwiftUI 应用于 `Result` 类型的键路径，用于获取对象的部分标识符。
- **animation**：因获取的结果发生变化而导致用户界面变化时使用的动画。

## 讨论

当您要配置一个包含多个谓词和排序描述符的获取请求时，请使用此初始化程序。例如，你可以从`Quake`托管对象（[doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed]示例代码项目定义用于存储地震数据）发出请求。通过为请求设置[doc://com.apple.documentation/documentation/CoreData/NSFetchRequest/fetchLimit]，将结果数量限制为`1000`：

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

使用请求定义`SectionedFetchedResults` 属性：

```swift
@SectionedFetchRequest<String, Quake>(
    fetchRequest: Quake.request,
    sectionIdentifier: \.day)
private var quakes: FetchedResults<String, Quake>
```

如果只需要配置请求的部分标识符、谓词和排序描述符，请使用 [init(sectionIdentifier:sortDescriptors:predicate:animation:)](init_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md) 代替。如果需要指定 [Transaction](../Transaction.zh-Hans.md)，而不是可选的[Animation](../Animation.zh-Hans.md)，请使用 [init(fetchRequest:sectionIdentifier:transaction:)](init_fetchRequest_sectionIdentifier_transaction.zh-Hans.md)。

## 创建完全配置的获取请求

- **init(fetchRequest:sectionIdentifier:transaction:)**：创建一个完全配置的分段获取请求，在更新结果时使用指定的事务。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(fetchRequest:sectionIdentifier:animation:)
crawled: 2025-12-02T18:48:26Z
---

# init(fetchRequest:sectionIdentifier:animation:)

**Initializer**

Creates a fully configured sectioned fetch request that uses the specified animation when updating results.

## Declaration

```swift
@MainActor @preconcurrency init(fetchRequest: NSFetchRequest<Result>, sectionIdentifier: KeyPath<Result, SectionIdentifier>, animation: Animation? = nil)
```

## Parameters

- **fetchRequest**: An [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] instance that describes the search criteria for retrieving data from the persistent store.
- **sectionIdentifier**: A key path that SwiftUI applies to the `Result` type to get an object’s section identifier.
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

Use the request to define a `SectionedFetchedResults` property:

```swift
@SectionedFetchRequest<String, Quake>(
    fetchRequest: Quake.request,
    sectionIdentifier: \.day)
private var quakes: FetchedResults<String, Quake>
```

If you only need to configure the request’s section identifier, predicate, and sort descriptors, use [init(sectionIdentifier:sortDescriptors:predicate:animation:)](init_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md) instead. If you need to specify a [Transaction](../Transaction.zh-Hans.md) rather than an optional [Animation](../Animation.zh-Hans.md), use [init(fetchRequest:sectionIdentifier:transaction:)](init_fetchRequest_sectionIdentifier_transaction.zh-Hans.md).

## Creating a fully configured fetch request

- **init(fetchRequest:sectionIdentifier:transaction:)**: Creates a fully configured sectioned fetch request that uses the specified transaction when updating results.

