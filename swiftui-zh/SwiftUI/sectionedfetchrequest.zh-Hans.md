--- 来源：https://developer.apple.com/documentation/swiftui/sectionedfetchrequest
抓取时间：2025-12-02T18:48:06Z

---

# SectionedFetchRequest

**Structure**

一种属性包装器类型，用于从 Core Data 持久化存储中检索按节分组的实体。

## 声明

```swift
@MainActor @propertyWrapper @preconcurrency struct SectionedFetchRequest<SectionIdentifier, Result> where SectionIdentifier : Hashable, Result : NSFetchRequestResult
```

## 概述

使用 `SectionedFetchRequest` 属性包装器来声明 [SectionedFetchResults](SectionedFetchResults.zh-Hans.md) 属性，该属性为 SwiftUI 视图提供分组的 Core Data 托管对象集合。如果不需要分节，请改用 [FetchRequest](FetchRequest.zh-Hans.md)。

配置一个分段获取请求，其中包含可选的谓词和排序描述符，并包含一个 `sectionIdentifier` 参数来指示如何对获取的结果进行分组。请确保选择的排序和分段方式能够协同工作，以避免出现不连续的分段。例如，您可以请求一个地震列表，该列表由 ⟦IL_0019⟧ 示例代码项目定义的用于存储地震数据的 `Quake` 托管对象组成，并按时间排序，按日期分组：

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

始终将具有分段获取请求包装器的属性声明为私有属性。这样，编译器可以帮助您避免意外地从封闭视图的成员初始化器中设置该属性。

请求会根据您指定的 `Result` 类型推断实体类型，在上面的示例中，该类型为 `Quake`。指定一个 `SectionIdentifier` 类型，以声明从获取的对象 `sectionIdentifier` 键路径中找到的类型。节标识符类型必须符合 [doc://com.apple.documentation/documentation/Swift/Hashable] 协议。

上面的示例依赖于 `Quake` 类型，该类型具有一个 `day` 属性，该属性可以是存储字符串或计算字符串。务必使用 `@objc` 属性标记任何计算属性，使其能够用作节标识符。为了获得处理大型数据集的最佳性能，请使用存储属性。

分段获取请求及其结果使用存储在环境中的托管对象上下文，您可以使用 [managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) 环境值访问该上下文。为了支持用户界面活动，您通常依赖于共享实例的属性。例如，您可以使用在模型中定义的共享容器，在顶级内容视图上设置上下文：

CB_0003

当您需要动态更改节标识符、谓词或排序描述符时，可以直接或通过绑定访问请求的 DL_0014 结构。

## 创建获取请求

- SY_0033：基于节标识符、谓词和引用类型排序参数创建分段获取请求。

- SY_0032：基于节标识符、谓词和排序参数，为指定的实体描述创建分段获取请求。

## 创建完全配置的获取请求

- **init(fetchRequest:sectionIdentifier:animation:)**：创建一个完全配置的分段式获取请求，该请求在更新结果时使用指定的动画。

- **init(fetchRequest:sectionIdentifier:transaction:)**：创建一个完全配置的分段式获取请求，该请求在更新结果时使用指定的事务。

## 动态配置请求

- **SectionedFetchRequest.Configuration**：请求的可配置属性。

- **projectedValue**：请求可变配置属性的绑定。

## 获取已获取的结果

- **update()**：更新已获取的结果。

- **wrappedValue**：获取请求的已获取结果。

## 默认实现

- **动态属性实现**

## 访问核心数据

- **加载和显示大型数据源**：在后台处理数据，并通过批量导入和防止重复记录来降低内存使用量。

- **managedObjectContext**

- **FetchRequest**：一种属性包装类型，用于从核心数据持久存储中检索实体。

- **FetchedResults**：从核心数据存储中检索的结果集合。

- **SectionedFetchResults**：从核心数据持久存储中检索的结果集合，并按部分进行分组。

## 符合以下规范

- Copyable

- DynamicProperty


---
source: https://developer.apple.com/documentation/swiftui/sectionedfetchrequest
crawled: 2025-12-02T18:48:06Z
---

# SectionedFetchRequest

**Structure**

A property wrapper type that retrieves entities, grouped into sections, from a Core Data persistent store.

## Declaration

```swift
@MainActor @propertyWrapper @preconcurrency struct SectionedFetchRequest<SectionIdentifier, Result> where SectionIdentifier : Hashable, Result : NSFetchRequestResult
```

## Overview

Use a `SectionedFetchRequest` property wrapper to declare a [SectionedFetchResults](SectionedFetchResults.zh-Hans.md) property that provides a grouped collection of Core Data managed objects to a SwiftUI view. If you don’t need sectioning, use [FetchRequest](FetchRequest.zh-Hans.md) instead.

Configure a sectioned fetch request with an optional predicate and sort descriptors, and include a `sectionIdentifier` parameter to indicate how to group the fetched results. Be sure that you choose sorting and sectioning that work together to avoid discontiguous sections. For example, you can request a list of earthquakes, composed of `Quake` managed objects that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines to store earthquake data, sorted by time and grouped by date:

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

Always declare properties that have a sectioned fetch request wrapper as private. This lets the compiler help you avoid accidentally setting the property from the memberwise initializer of the enclosing view.

The request infers the entity type from the `Result` type that you specify, which is `Quake` in the example above. Indicate a `SectionIdentifier` type to declare the type found at the fetched object’s `sectionIdentifier` key path. The section identifier type must conform to the [doc://com.apple.documentation/documentation/Swift/Hashable] protocol.

The example above depends on the `Quake` type having a `day` property that’s either a stored or computed string. Be sure to mark any computed property with the `@objc` attribute for it to function as a section identifier. For best performance with large data sets, use stored properties.

The sectioned fetch request and its results use the managed object context stored in the environment, which you can access using the [managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) environment value. To support user interface activity, you typically rely on the [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] property of a shared [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] instance. For example, you can set a context on your top-level content view using a shared container that you define as part of your model:

```swift
ContentView()
    .environment(
        \.managedObjectContext,
        QuakesProvider.shared.container.viewContext)
```

When you need to dynamically change the section identifier, predicate, or sort descriptors, access the request’s [Configuration](SectionedFetchRequest/Configuration.zh-Hans.md) structure, either directly or with a binding.

## Creating a fetch request

- **init(sectionIdentifier:sortDescriptors:predicate:animation:)**: Creates a sectioned fetch request based on a section identifier, a predicate, and reference type sort parameters.
- **init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)**: Creates a sectioned fetch request for a specified entity description, based on a section identifier, a predicate, and sort parameters.

## Creating a fully configured fetch request

- **init(fetchRequest:sectionIdentifier:animation:)**: Creates a fully configured sectioned fetch request that uses the specified animation when updating results.
- **init(fetchRequest:sectionIdentifier:transaction:)**: Creates a fully configured sectioned fetch request that uses the specified transaction when updating results.

## Configuring a request dynamically

- **SectionedFetchRequest.Configuration**: The request’s configurable properties.
- **projectedValue**: A binding to the request’s mutable configuration properties.

## Getting the fetched results

- **update()**: Updates the fetched results.
- **wrappedValue**: The fetched results of the fetch request.

## Default Implementations

- **DynamicProperty Implementations**

## Accessing Core Data

- **Loading and displaying a large data feed**: Consume data in the background, and lower memory use by batching imports and preventing duplicate records.
- **managedObjectContext**
- **FetchRequest**: A property wrapper type that retrieves entities from a Core Data persistent store.
- **FetchedResults**: A collection of results retrieved from a Core Data store.
- **SectionedFetchResults**: A collection of results retrieved from a Core Data persistent store, grouped into sections.

## Conforms To

- Copyable
- DynamicProperty

