---
来源：https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)
抓取时间：2025-11-30T22:32:48Z


# init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)

**Initializer**

根据分节标识符、谓词和排序参数，为指定的实体描述创建分节提取请求。

### 声明

```swift
@MainActor @preconcurrency init(entity: NSEntityDescription, sectionIdentifier: KeyPath<Result, SectionIdentifier>, sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## 参数

- **entity**：要获取的核心数据实体的描述。
- **sectionIdentifier**：SwiftUI 应用于 `Result` 类型的关键路径，用于获取对象的部分标识符。
- **sortDescriptors**：定义获取结果排序顺序的排序描述符数组。
- **predicate**：一个[doc://com.apple.documentation/documentation/Foundation/NSPredicate]实例，定义用于过滤获取结果的逻辑条件。
- **animation**：因获取的结果发生变化而导致用户界面变化时使用的动画。

## 讨论

如果需要明确指定请求的实体类型，请使用此初始化程序。如果在请求声明中指定了一个占位符`Result` 类型，则可以使用[init(sectionIdentifier:sortDescriptors:predicate:animation:)](init_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md) 初始化器让请求推断出实体类型。如果需要对获取请求配置进行更多控制，请使用 [init(fetchRequest:sectionIdentifier:animation:)](init_fetchRequest_sectionIdentifier_animation.zh-Hans.md)。

## 创建获取请求

- **init(sectionIdentifier:sortDescriptors:predicate:animation:)**：根据分段标识符、谓词和引用类型排序参数创建分段取回请求。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)
crawled: 2025-11-30T22:32:48Z
---

# init(entity:sectionIdentifier:sortDescriptors:predicate:animation:)

**Initializer**

Creates a sectioned fetch request for a specified entity description, based on a section identifier, a predicate, and sort parameters.

## Declaration

```swift
@MainActor @preconcurrency init(entity: NSEntityDescription, sectionIdentifier: KeyPath<Result, SectionIdentifier>, sortDescriptors: [NSSortDescriptor], predicate: NSPredicate? = nil, animation: Animation? = nil)
```

## Parameters

- **entity**: The description of the Core Data entity to fetch.
- **sectionIdentifier**: A key path that SwiftUI applies to the `Result` type to get an object’s section identifier.
- **sortDescriptors**: An array of sort descriptors that define the sort order of the fetched results.
- **predicate**: An [doc://com.apple.documentation/documentation/Foundation/NSPredicate] instance that defines logical conditions used to filter the fetched results.
- **animation**: The animation to use for user interface changes that result from changes to the fetched results.

## Discussion

Use this initializer if you need to explicitly specify the entity type for the request. If you specify a placeholder `Result` type in the request declaration, use the [init(sectionIdentifier:sortDescriptors:predicate:animation:)](init_sectionIdentifier_sortDescriptors_predicate_animation.zh-Hans.md) initializer to let the request infer the entity type. If you need more control over the fetch request configuration, use [init(fetchRequest:sectionIdentifier:animation:)](init_fetchRequest_sectionIdentifier_animation.zh-Hans.md).

## Creating a fetch request

- **init(sectionIdentifier:sortDescriptors:predicate:animation:)**: Creates a sectioned fetch request based on a section identifier, a predicate, and reference type sort parameters.

