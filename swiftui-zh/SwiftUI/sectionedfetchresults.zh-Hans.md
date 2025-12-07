---
来源： https://developer.apple.com/documentation/swiftui/sectionedfetchresults
抓取时间： 2025-12-02T18:48:07Z
---

# SectionedFetchResults

**Structure**

从 Core Data 持久性存储检索的结果集合，按部分分组。

## 声明

```swift
@MainActor @preconcurrency struct SectionedFetchResults<SectionIdentifier, Result> where SectionIdentifier : Hashable, Result : NSFetchRequestResult
```

## 概览

使用`SectionedFetchResults` 实例可在应用程序的用户界面中显示或编辑按部分分组的 Core Data 托管对象。如果不需要分区，请使用 [FetchedResults](FetchedResults.zh-Hans.md) 代替。

通过使用[SectionedFetchRequest](SectionedFetchRequest.zh-Hans.md) 属性包装器注解获取的结果属性声明，您可以请求一组特定的结果。用`Results` 类型表示获取的实体类型，用`SectionIdentifier` 类型表示区分各部分的标识符类型。例如，您可以创建一个请求，列出[doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] 示例代码项目定义用于存储地震数据的所有`Quake` 受管对象，这些对象按其`time` 属性排序，并按表示地震发生天数的字符串分组：

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

`quakes`属性是[Section](SectionedFetchResults/Section.zh-Hans.md) 实例的集合，每个实例包含`Quake` 实例的集合。上面的示例依赖于`Quake` 模型对象声明`time` 和`day` 属性，这些属性可以是存储的，也可以是计算的。为了在处理大型数据集时获得最佳性能，请使用存储属性。

部分集合以及每个部分中的托管对象集合都符合[doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] 协议，因此可以像访问其他集合一样访问它们。例如，您可以在[ForEach](ForEach.zh-Hans.md) 循环内创建嵌套[List](List.zh-Hans.md) 循环，以遍历结果：

```swift
List {
    ForEach(quakes) { section in
        Section(header: Text(section.id)) {
            ForEach(section) { quake in
                QuakeRow(quake: quake) // Displays information about a quake.
            }
        }
    }
}
```

不要将用于创建分层显示的[Section](Section.zh-Hans.md) 视图与保存提取结果的[Section](SectionedFetchResults/Section.zh-Hans.md) 实例混淆。

当需要动态更改请求的部分标识符、谓词或排序描述符时，可分别设置结果实例的 [sectionIdentifier](SectionedFetchResults/sectionIdentifier.zh-Hans.md)、[nsPredicate](SectionedFetchResults/nsPredicate.zh-Hans.md) 和 [sortDescriptors](SectionedFetchResults/sortDescriptors.zh-Hans.md) 或 [nsSortDescriptors](SectionedFetchResults/nsSortDescriptors.zh-Hans.md) 属性。确保排序和分段同时进行，以避免出现不连贯的分段。

获取请求及其结果使用的是存储在环境中的托管对象上下文，你可以使用 [managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) 环境值访问该上下文。要支持用户界面活动，通常需要依赖共享[doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] 实例的[doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] 属性。例如，您可以使用定义为模型一部分的容器在顶层内容视图上设置上下文：

```swift
ContentView()
    .environment(
        \.managedObjectContext,
        QuakesProvider.shared.container.viewContext)
```

## 配置相关的分段获取请求

- **nsPredicate**：请求的谓词。
- **sortDescriptors**：请求的排序描述符，作为值类型访问。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。
- **sectionIdentifier**：系统用于将获取的结果分组的关键路径。
- **SectionedFetchResults.Section**：共享指定标识符的提取结果集合。

## 获取索引

- **startIndex**：结果集合中第一个部分的索引。
- **endIndex**：比最后一节索引大一位的索引。

## 获取结果

- **subscript(_:)**：获取指定索引处的部分。

## 访问核心数据

- 加载并显示大型数据源**：在后台消耗数据，并通过批量导入和防止重复记录来降低内存使用率。
- **managedObjectContext**
- **FetchRequest**：从 Core Data 持久化存储中检索实体的属性包装器类型。
- **FetchedResults**：从 Core Data 存储检索结果的集合。
- **SectionedFetchRequest**：属性包装器类型，用于从核心数据持久性存储中检索按部分分组的实体。

## 符合

- 双向集合
- 双向集合
- 随机访问集合
- 可发送
- 可发送元类型
- 序列


---
source: https://developer.apple.com/documentation/swiftui/sectionedfetchresults
crawled: 2025-12-02T18:48:07Z
---

# SectionedFetchResults

**Structure**

A collection of results retrieved from a Core Data persistent store, grouped into sections.

## Declaration

```swift
@MainActor @preconcurrency struct SectionedFetchResults<SectionIdentifier, Result> where SectionIdentifier : Hashable, Result : NSFetchRequestResult
```

## Overview

Use a `SectionedFetchResults` instance to show or edit Core Data managed objects, grouped into sections, in your app’s user interface. If you don’t need sectioning, use [FetchedResults](FetchedResults.zh-Hans.md) instead.

You request a particular set of results by annotating the fetched results property declaration with a [SectionedFetchRequest](SectionedFetchRequest.zh-Hans.md) property wrapper. Indicate the type of the fetched entities with a `Results` type, and the type of the identifier that distinguishes the sections with a `SectionIdentifier` type. For example, you can create a request to list all `Quake` managed objects that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines to store earthquake data, sorted by their `time` property and grouped by a string that represents the days when earthquakes occurred:

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

The `quakes` property acts as a collection of [Section](SectionedFetchResults/Section.zh-Hans.md) instances, each containing a collection of `Quake` instances. The example above depends on the `Quake` model object declaring both `time` and `day` properties, either stored or computed. For best performance with large data sets, use stored properties.

The collection of sections, as well as the collection of managed objects in each section, conforms to the [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] protocol, so you can access them as you would any other collection. For example, you can create nested [ForEach](ForEach.zh-Hans.md) loops inside a [List](List.zh-Hans.md) to iterate over the results:

```swift
List {
    ForEach(quakes) { section in
        Section(header: Text(section.id)) {
            ForEach(section) { quake in
                QuakeRow(quake: quake) // Displays information about a quake.
            }
        }
    }
}
```

Don’t confuse the [Section](Section.zh-Hans.md) view that you use to create a hierarchical display with the [Section](SectionedFetchResults/Section.zh-Hans.md) instances that hold the fetched results.

When you need to dynamically change the request’s section identifier, predicate, or sort descriptors, set the result instance’s [sectionIdentifier](SectionedFetchResults/sectionIdentifier.zh-Hans.md), [nsPredicate](SectionedFetchResults/nsPredicate.zh-Hans.md), and [sortDescriptors](SectionedFetchResults/sortDescriptors.zh-Hans.md) or [nsSortDescriptors](SectionedFetchResults/nsSortDescriptors.zh-Hans.md) properties, respectively. Be sure that the sorting and sectioning work together to avoid discontinguous sections.

The fetch request and its results use the managed object context stored in the environment, which you can access using the [managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) environment value. To support user interface activity, you typically rely on the [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] property of a shared [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] instance. For example, you can set a context on your top-level content view using a container that you define as part of your model:

```swift
ContentView()
    .environment(
        \.managedObjectContext,
        QuakesProvider.shared.container.viewContext)
```

## Configuring the associated sectioned fetch request

- **nsPredicate**: The request’s predicate.
- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.
- **sectionIdentifier**: The key path that the system uses to group fetched results into sections.
- **SectionedFetchResults.Section**: A collection of fetched results that share a specified identifier.

## Getting indices

- **startIndex**: The index of the first section in the results collection.
- **endIndex**: The index that’s one greater than that of the last section.

## Getting results

- **subscript(_:)**: Gets the section at the specified index.

## Accessing Core Data

- **Loading and displaying a large data feed**: Consume data in the background, and lower memory use by batching imports and preventing duplicate records.
- **managedObjectContext**
- **FetchRequest**: A property wrapper type that retrieves entities from a Core Data persistent store.
- **FetchedResults**: A collection of results retrieved from a Core Data store.
- **SectionedFetchRequest**: A property wrapper type that retrieves entities, grouped into sections, from a Core Data persistent store.

## Conforms To

- BidirectionalCollection
- Collection
- RandomAccessCollection
- Sendable
- SendableMetatype
- Sequence

