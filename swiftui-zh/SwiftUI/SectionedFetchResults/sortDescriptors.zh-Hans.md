---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/sortDescriptors
抓取时间： 2025-12-02T18:48:38Z
---

# 排序描述符

**实例属性**

请求的排序描述符，以值类型访问。

## 声明

```swift
@MainActor @preconcurrency var sortDescriptors: [SortDescriptor<Result>] { get nonmutating set }
```

## 讨论

设置此值可使关联的[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) 使用新的[doc://com.apple.documentation/documentation/Foundation/SortDescriptor] 实例集合执行获取。结果集合中存储的实体顺序可能会因此改变。请按照[Configuration](../SectionedFetchRequest/Configuration.zh-Hans.md) 中的说明，小心协调部分和排序更新。

如果要使用 [doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] 实例，请设置 [nsSortDescriptors](nsSortDescriptors.zh-Hans.md) 代替。

## 配置相关的分段获取请求

- **nsPredicate**：请求的谓词。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。
- **sectionIdentifier**：系统用于将获取的结果分组的关键路径。
- **SectionedFetchResults.Section**：共享指定标识符的提取结果集合。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/sortDescriptors
crawled: 2025-12-02T18:48:38Z
---

# sortDescriptors

**Instance Property**

The request’s sort descriptors, accessed as value types.

## Declaration

```swift
@MainActor @preconcurrency var sortDescriptors: [SortDescriptor<Result>] { get nonmutating set }
```

## Discussion

Set this value to cause the associated [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) to execute a fetch with a new collection of [doc://com.apple.documentation/documentation/Foundation/SortDescriptor] instances. The order of entities stored in the results collection may change as a result. Use care to coordinate section and sort updates, as described in [Configuration](../SectionedFetchRequest/Configuration.zh-Hans.md).

If you want to use [doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] instances, set [nsSortDescriptors](nsSortDescriptors.zh-Hans.md) instead.

## Configuring the associated sectioned fetch request

- **nsPredicate**: The request’s predicate.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.
- **sectionIdentifier**: The key path that the system uses to group fetched results into sections.
- **SectionedFetchResults.Section**: A collection of fetched results that share a specified identifier.

