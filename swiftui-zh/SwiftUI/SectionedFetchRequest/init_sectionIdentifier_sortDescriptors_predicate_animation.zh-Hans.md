---
来源：https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(sectionIdentifier:sortDescriptors:predicate:animation:)
抓取时间：2025-11-30T22:32:47Z
---

# init(sectionIdentifier:sortDescriptors:predicate:animation:)

**Initializer**

根据分节标识符、谓词和引用类型排序参数创建分节提取请求。

### 声明

```swift
@MainActor @preconcurrency init(sectionIdentifier: KeyPath<Result, SectionIdentifier>, sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## 参数

- **sectionIdentifier**：SwiftUI 应用于 `Result` 类型的键路径，用于获取对象的部分标识符。
- **sortDescriptors**：定义获取结果排序顺序的排序描述符数组。
- **predicate**：一个[doc://com.apple.documentation/documentation/Foundation/NSPredicate]实例，定义用于过滤获取结果的逻辑条件。
- **animation**：因获取的结果发生变化而导致用户界面变化时使用的动画。

## 讨论

请求通过调用托管对象的 [doc://com.apple.documentation/documentation/CoreData/NSManagedObject/entity()] type 方法，从 `Result` 实例获取实体类型。如果需要明确指定实体类型，请使用 [init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)](init_entity_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md) 初始化器。如果需要对获取请求配置进行更多控制，请使用 [init(fetchRequest:sectionIdentifier:animation:)](init_fetchRequest_sectionIdentifier_animation.zh-Hans.md)。对于值类型排序描述符，请使用 [init(sectionIdentifier:sortDescriptors:predicate:animation:)](init_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md)。

## 创建获取请求

- **init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)**：根据分节标识符、谓词和排序参数，为指定的实体描述创建分节取回请求。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(sectionIdentifier:sortDescriptors:predicate:animation:)
crawled: 2025-11-30T22:32:47Z
---

# init(sectionIdentifier:sortDescriptors:predicate:animation:)

**Initializer**

Creates a sectioned fetch request based on a section identifier, a predicate, and reference type sort parameters.

## Declaration

```swift
@MainActor @preconcurrency init(sectionIdentifier: KeyPath<Result, SectionIdentifier>, sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## Parameters

- **sectionIdentifier**: A key path that SwiftUI applies to the `Result` type to get an object’s section identifier.
- **sortDescriptors**: An array of sort descriptors that define the sort order of the fetched results.
- **predicate**: An [doc://com.apple.documentation/documentation/Foundation/NSPredicate] instance that defines logical conditions used to filter the fetched results.
- **animation**: The animation to use for user interface changes that result from changes to the fetched results.

## Discussion

The request gets the entity type from the `Result` instance by calling that managed object’s [doc://com.apple.documentation/documentation/CoreData/NSManagedObject/entity()] type method. If you need to specify the entity type explicitly, use the [init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)](init_entity_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md) initializer instead. If you need more control over the fetch request configuration, use [init(fetchRequest:sectionIdentifier:animation:)](init_fetchRequest_sectionIdentifier_animation.zh-Hans.md). For value type sort descriptors, use [init(sectionIdentifier:sortDescriptors:predicate:animation:)](init_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md).

## Creating a fetch request

- **init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)**: Creates a sectioned fetch request for a specified entity description, based on a section identifier, a predicate, and sort parameters.

