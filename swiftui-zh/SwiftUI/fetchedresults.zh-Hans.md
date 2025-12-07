---
来源： https://developer.apple.com/documentation/swiftui/fetchedresults
抓取时间： 2025-12-02T18:48:05Z
---

# 抓取结果

**Structure**

从核心数据存储检索到的结果集合。

## 声明

```swift
@MainActor @preconcurrency struct FetchedResults<Result> where Result : NSFetchRequestResult
```

## 概览

使用`FetchedResults` 实例可在应用程序的用户界面中显示或编辑 Core Data 托管对象。您可以指定`Result` 类型作为实体类型，并使用[FetchRequest](FetchRequest.zh-Hans.md) 属性包装器注解获取的结果属性声明，从而请求一组特定的结果。例如，你可以创建一个请求来列出所有`Quake`托管对象，这些对象是[doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed]示例代码项目定义用于存储地震数据的，并按`time`属性排序：

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake>
```

结果实例符合 [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection]，因此您可以像访问其他集合一样访问它。例如，你可以创建一个遍历所有结果的[List](List.zh-Hans.md)：

```swift
List(quakes) { quake in
    NavigationLink(destination: QuakeDetail(quake: quake)) {
        QuakeRow(quake: quake)
    }
}
```

当需要动态更改请求的谓词或排序描述符时，可分别设置结果实例的 [nsPredicate](FetchedResults/nsPredicate.zh-Hans.md) 和 [sortDescriptors](FetchedResults/sortDescriptors.zh-Hans.md) 或 [nsSortDescriptors](FetchedResults/nsSortDescriptors.zh-Hans.md) 属性。

获取请求及其结果使用的是存储在环境中的托管对象上下文，你可以使用 [managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) 环境值访问该上下文。要支持用户界面活动，通常需要依赖共享[doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] 实例的[doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] 属性。例如，您可以使用定义为模型一部分的容器在顶层内容视图上设置上下文：

```swift
ContentView()
    .environment(
        \.managedObjectContext,
        QuakesProvider.shared.container.viewContext)
```

## 配置相关的获取请求

- **nsPredicate**：请求的谓词。
- **sortDescriptors**：请求的排序描述符，作为值类型访问。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。

## 获取索引

- **startIndex**：结果集合中第一个实体的索引。
- **endIndex**：比最后一个有效下标参数大一位的索引。

## 获取结果

- **subscript(_:)**：获取指定索引处的实体。

## 访问核心数据

- 加载并显示大型数据源**：在后台消耗数据，并通过批量导入和防止重复记录来降低内存使用率。
- **managedObjectContext**
- **FetchRequest**：一种属性包装器类型，用于从 Core Data 持久化存储中检索实体。
- **SectionedFetchRequest**：一种属性包装器类型，用于从 Core Data 持久性存储中检索按部分分组的实体。
- **SectionedFetchResults**：从 Core Data 持久性存储中检索的结果集合，按部分分组。

## 符合

- 双向集合
- 集合
- 随机访问集合
- 可发送
- 可发送元类型
- 序列


---
source: https://developer.apple.com/documentation/swiftui/fetchedresults
crawled: 2025-12-02T18:48:05Z
---

# FetchedResults

**Structure**

A collection of results retrieved from a Core Data store.

## Declaration

```swift
@MainActor @preconcurrency struct FetchedResults<Result> where Result : NSFetchRequestResult
```

## Overview

Use a `FetchedResults` instance to show or edit Core Data managed objects in your app’s user interface. You request a particular set of results by specifying a `Result` type as the entity type, and annotating the fetched results property declaration with a [FetchRequest](FetchRequest.zh-Hans.md) property wrapper. For example, you can create a request to list all `Quake` managed objects that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines to store earthquake data, sorted by their `time` property:

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake>
```

The results instance conforms to [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection], so you access it like any other collection. For example, you can create a [List](List.zh-Hans.md) that iterates over all the results:

```swift
List(quakes) { quake in
    NavigationLink(destination: QuakeDetail(quake: quake)) {
        QuakeRow(quake: quake)
    }
}
```

When you need to dynamically change the request’s predicate or sort descriptors, set the result instance’s [nsPredicate](FetchedResults/nsPredicate.zh-Hans.md) and [sortDescriptors](FetchedResults/sortDescriptors.zh-Hans.md) or [nsSortDescriptors](FetchedResults/nsSortDescriptors.zh-Hans.md) properties, respectively.

The fetch request and its results use the managed object context stored in the environment, which you can access using the [managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) environment value. To support user interface activity, you typically rely on the [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] property of a shared [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] instance. For example, you can set a context on your top level content view using a container that you define as part of your model:

```swift
ContentView()
    .environment(
        \.managedObjectContext,
        QuakesProvider.shared.container.viewContext)
```

## Configuring the associated fetch request

- **nsPredicate**: The request’s predicate.
- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.

## Getting indices

- **startIndex**: The index of the first entity in the results collection.
- **endIndex**: The index that’s one greater than the last valid subscript argument.

## Getting results

- **subscript(_:)**: Gets the entity at the specified index.

## Accessing Core Data

- **Loading and displaying a large data feed**: Consume data in the background, and lower memory use by batching imports and preventing duplicate records.
- **managedObjectContext**
- **FetchRequest**: A property wrapper type that retrieves entities from a Core Data persistent store.
- **SectionedFetchRequest**: A property wrapper type that retrieves entities, grouped into sections, from a Core Data persistent store.
- **SectionedFetchResults**: A collection of results retrieved from a Core Data persistent store, grouped into sections.

## Conforms To

- BidirectionalCollection
- Collection
- RandomAccessCollection
- Sendable
- SendableMetatype
- Sequence

