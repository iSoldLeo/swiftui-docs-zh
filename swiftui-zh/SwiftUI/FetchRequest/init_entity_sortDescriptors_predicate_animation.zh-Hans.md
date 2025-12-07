--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(entity:sortDescriptors:predicate:animation:)

抓取时间：2025-11-30T22:32:31Z

---

# init(entity:sortDescriptors:predicate:animation:)

**Initializer**

根据谓词和排序参数，为指定的实体描述创建获取请求。

## 声明

```swift
@MainActor @preconcurrency init(entity: NSEntityDescription, sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## 参数

- **entity**：要获取的 Core Data 实体的描述。

- **sortDescriptors**：定义获取结果排序顺序的排序描述符数组。

- **predicate**：一个 [doc://com.apple.documentation/documentation/Foundation/NSPredicate] 实例，用于定义过滤获取结果的逻辑条件。

- **animation**：用于用户界面因获取结果更改而产生的动画。

## 讨论

如果需要显式指定请求的实体类型，请使用此初始化器。如果在请求声明中指定了占位符 `Result` 类型，请使用 [init(sortDescriptors:predicate:animation:)](init_sortDescriptors_predicate_animation.zh-Hans.md) 初始化器，让请求推断实体类型。如果需要对获取请求配置进行更多控制，请使用 [init(fetchRequest:animation:)](init_fetchRequest_animation.zh-Hans.md)。

## 创建获取请求

- **init(sortDescriptors:predicate:animation:)**：基于谓词和引用类型排序参数创建获取请求。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(entity:sortDescriptors:predicate:animation:)
crawled: 2025-11-30T22:32:31Z
---

# init(entity:sortDescriptors:predicate:animation:)

**Initializer**

Creates a fetch request for a specified entity description, based on a predicate and sort parameters.

## Declaration

```swift
@MainActor @preconcurrency init(entity: NSEntityDescription, sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## Parameters

- **entity**: The description of the Core Data entity to fetch.
- **sortDescriptors**: An array of sort descriptors that define the sort order of the fetched results.
- **predicate**: An [doc://com.apple.documentation/documentation/Foundation/NSPredicate] instance that defines logical conditions used to filter the fetched results.
- **animation**: The animation to use for user interface changes that result from changes to the fetched results.

## Discussion

Use this initializer if you need to explicitly specify the entity type for the request. If you specify a placeholder `Result` type in the request declaration, use the [init(sortDescriptors:predicate:animation:)](init_sortDescriptors_predicate_animation.zh-Hans.md) initializer to let the request infer the entity type. If you need more control over the fetch request configuration, use [init(fetchRequest:animation:)](init_fetchRequest_animation.zh-Hans.md).

## Creating a fetch request

- **init(sortDescriptors:predicate:animation:)**: Creates a fetch request based on a predicate and reference type sort parameters.

