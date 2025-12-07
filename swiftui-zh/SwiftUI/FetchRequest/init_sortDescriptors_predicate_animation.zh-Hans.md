--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(sortDescriptors:predicate:animation:)

抓取时间：2025-12-02T18:48:08Z

---

# init(sortDescriptors:predicate:animation:)

**Initializer**

基于谓词和引用类型排序参数创建获取请求。

## 声明

```swift
@MainActor @preconcurrency init(sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## 参数

- **sortDescriptors**：定义获取结果排序顺序的排序描述符数组。

- **predicate**：定义用于过滤获取结果的逻辑条件的 [doc://com.apple.documentation/documentation/Foundation/NSPredicate] 实例。

- **animation**：用于用户界面因获取结果的变化而产生的动画效果。

## 讨论

请求通过调用托管对象的 [doc://com.apple.documentation/documentation/CoreData/NSManagedObject/entity()] type 方法，从 `Result` 实例获取实体类型。如果需要显式指定实体类型，请改用 [init(entity:sortDescriptors:predicate:animation:)](init_entity_sortDescriptors_predicate_animation.zh-Hans.md) 初始化器。如果需要对获取请求配置进行更多控制，请使用 [init(fetchRequest:animation:)](init_fetchRequest_animation.zh-Hans.md)。

## 创建获取请求

- **init(entity:sortDescriptors:predicate:animation:)**：根据谓词和排序参数，为指定的实体描述创建获取请求。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/init(sortDescriptors:predicate:animation:)
crawled: 2025-12-02T18:48:08Z
---

# init(sortDescriptors:predicate:animation:)

**Initializer**

Creates a fetch request based on a predicate and reference type sort parameters.

## Declaration

```swift
@MainActor @preconcurrency init(sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## Parameters

- **sortDescriptors**: An array of sort descriptors that define the sort order of the fetched results.
- **predicate**: An [doc://com.apple.documentation/documentation/Foundation/NSPredicate] instance that defines logical conditions used to filter the fetched results.
- **animation**: The animation to use for user interface changes that result from changes to the fetched results.

## Discussion

The request gets the entity type from the `Result` instance by calling that managed object’s [doc://com.apple.documentation/documentation/CoreData/NSManagedObject/entity()] type method. If you need to specify the entity type explicitly, use the [init(entity:sortDescriptors:predicate:animation:)](init_entity_sortDescriptors_predicate_animation.zh-Hans.md) initializer instead. If you need more control over the fetch request configuration, use [init(fetchRequest:animation:)](init_fetchRequest_animation.zh-Hans.md).

## Creating a fetch request

- **init(entity:sortDescriptors:predicate:animation:)**: Creates a fetch request for a specified entity description, based on a predicate and sort parameters.

