---
来源：https://developer.apple.com/documentation/swiftui/fetchrequest
抓取时间： 2025-12-02T18:48:05Z
---

# FetchRequest

**Structure**

一种属性包装器类型，用于从 Core Data 持久化存储中检索实体。

### 声明

```swift
@MainActor @propertyWrapper @preconcurrency struct FetchRequest<Result> where Result : NSFetchRequestResult
```

## 概览

使用`FetchRequest` 属性包装器声明[FetchedResults](FetchedResults.zh-Hans.md) 属性，该属性可向 SwiftUI 视图提供 Core Data 托管对象集合。请求会从您指定的`Result` 占位符类型推断出实体类型。使用可选谓词和排序描述符为请求设置条件。例如，您可以创建一个请求，列出[doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] 示例代码项目定义用于存储地震数据的所有`Quake` 托管对象，并按其 `time` 属性排序：

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake> // Define Quake in your model.
```

另外，如果您需要更大的灵活性，也可以使用已配置的[doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] 实例来初始化请求：

```swift
@FetchRequest(fetchRequest: request)
private var quakes: FetchedResults<Quake>
```

始终将具有获取请求包装器的属性声明为私有。这样，编译器就可以帮助你避免意外地从外层视图的成员初始化器中设置属性。

获取请求及其结果使用存储在环境中的托管对象上下文，您可以使用[managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) 环境值访问该上下文。要支持用户界面活动，通常需要依赖共享[doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] 实例的[doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] 属性。例如，您可以使用定义为模型一部分的共享容器在顶层内容视图上设置上下文：

```swift
ContentView()
    .environment(
        \.managedObjectContext,
        QuakesProvider.shared.container.viewContext)
```

当需要动态更改谓词或排序描述符时，请访问请求的 [Configuration](FetchRequest/Configuration.zh-Hans.md) 结构。如果要创建一个请求，根据所获取结果的共同特征对其进行分组，请使用 [SectionedFetchRequest](SectionedFetchRequest.zh-Hans.md)。

## 创建获取请求

- **init(sortDescriptors:predicate:animation:)**：根据谓词和引用类型排序参数创建提取请求。
- **init(entity:sortDescriptors:predicate:animation:)**：根据谓词和排序参数为指定的实体描述创建取回请求。

## 创建一个完全配置的提取请求

- **init(fetchRequest:animation:)**：创建一个完全配置的获取请求，在更新结果时使用指定的动画。
- **init(fetchRequest:transaction:)**：创建完全配置的提取请求，更新结果时使用指定的事务。

## 动态配置请求

- **FetchRequest.Configuration**：请求的可配置属性。
- **projectedValue**：与请求的可变配置属性绑定。

## 获取获取的结果

- **update()**：更新获取的结果。
- **wrappedValue**：获取请求的提取结果。

## 默认实现

- **动态属性实现**

## 访问核心数据

- 加载并显示大型数据源**：在后台消耗数据，并通过批量导入和防止重复记录来降低内存使用。
- **managedObjectContext**
- **FetchedResults**：从核心数据存储检索到的结果集合。
- **SectionedFetchRequest**：一种属性包装器类型，可从 Core Data 持久存储中检索按部分分组的实体。
- **SectionedFetchResults**：从 Core Data 持久性存储中检索的结果集合，按部分分组。

## 符合

- 可复制
- 动态属性
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/fetchrequest
crawled: 2025-12-02T18:48:05Z
---

# FetchRequest

**Structure**

A property wrapper type that retrieves entities from a Core Data persistent store.

## Declaration

```swift
@MainActor @propertyWrapper @preconcurrency struct FetchRequest<Result> where Result : NSFetchRequestResult
```

## Overview

Use a `FetchRequest` property wrapper to declare a [FetchedResults](FetchedResults.zh-Hans.md) property that provides a collection of Core Data managed objects to a SwiftUI view. The request infers the entity type from the `Result` placeholder type that you specify. Condition the request with an optional predicate and sort descriptors. For example, you can create a request to list all `Quake` managed objects that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines to store earthquake data, sorted by their `time` property:

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake> // Define Quake in your model.
```

Alternatively, when you need more flexibility, you can initialize the request with a configured [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest] instance:

```swift
@FetchRequest(fetchRequest: request)
private var quakes: FetchedResults<Quake>
```

Always declare properties that have a fetch request wrapper as private. This lets the compiler help you avoid accidentally setting the property from the memberwise initializer of the enclosing view.

The fetch request and its results use the managed object context stored in the environment, which you can access using the [managedObjectContext](EnvironmentValues/managedObjectContext.zh-Hans.md) environment value. To support user interface activity, you typically rely on the [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer/viewContext] property of a shared [doc://com.apple.documentation/documentation/CoreData/NSPersistentContainer] instance. For example, you can set a context on your top level content view using a shared container that you define as part of your model:

```swift
ContentView()
    .environment(
        \.managedObjectContext,
        QuakesProvider.shared.container.viewContext)
```

When you need to dynamically change the predicate or sort descriptors, access the request’s [Configuration](FetchRequest/Configuration.zh-Hans.md) structure. To create a request that groups the fetched results according to a characteristic that they share, use [SectionedFetchRequest](SectionedFetchRequest.zh-Hans.md) instead.

## Creating a fetch request

- **init(sortDescriptors:predicate:animation:)**: Creates a fetch request based on a predicate and reference type sort parameters.
- **init(entity:sortDescriptors:predicate:animation:)**: Creates a fetch request for a specified entity description, based on a predicate and sort parameters.

## Creating a fully configured fetch request

- **init(fetchRequest:animation:)**: Creates a fully configured fetch request that uses the specified animation when updating results.
- **init(fetchRequest:transaction:)**: Creates a fully configured fetch request that uses the specified transaction when updating results.

## Configuring a request dynamically

- **FetchRequest.Configuration**: The request’s configurable properties.
- **projectedValue**: A binding to the request’s mutable configuration properties.

## Getting the fetched results

- **update()**: Updates the fetched results.
- **wrappedValue**: The fetched results of the fetch request.

## Default Implementations

- **DynamicProperty Implementations**

## Accessing Core Data

- **Loading and displaying a large data feed**: Consume data in the background, and lower memory use by batching imports and preventing duplicate records.
- **managedObjectContext**
- **FetchedResults**: A collection of results retrieved from a Core Data store.
- **SectionedFetchRequest**: A property wrapper type that retrieves entities, grouped into sections, from a Core Data persistent store.
- **SectionedFetchResults**: A collection of results retrieved from a Core Data persistent store, grouped into sections.

## Conforms To

- Copyable
- DynamicProperty
- Sendable
- SendableMetatype

