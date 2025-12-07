---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/sectionIdentifier
抓取时间： 2025-12-02T18:48:40Z
---

# sectionIdentifier

**实例属性**

系统用于将获取的结果分组到各部分的关键路径。

## 声明

```swift
@MainActor @preconcurrency var sectionIdentifier: KeyPath<Result, SectionIdentifier> { get nonmutating set }
```

## 讨论

设置该值后，相关的[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) 将使用新的分段标识符执行获取操作，并生成更新的结果集合。更改该值会产生一组新的区段。请按照[Configuration](../SectionedFetchRequest/Configuration.zh-Hans.md) 中的说明，小心协调章节更新和排序更新。

## 配置相关的分段获取请求

- **nsPredicate**：请求的谓词。
- **sortDescriptors**：请求的排序描述符，作为值类型访问。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。
- **SectionedFetchResults.Section**：共享指定标识符的提取结果集合。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/sectionIdentifier
crawled: 2025-12-02T18:48:40Z
---

# sectionIdentifier

**Instance Property**

The key path that the system uses to group fetched results into sections.

## Declaration

```swift
@MainActor @preconcurrency var sectionIdentifier: KeyPath<Result, SectionIdentifier> { get nonmutating set }
```

## Discussion

Set this value to cause the associated [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) to execute a fetch with a new section identifier, producing an updated collection of results. Changing this value produces a new set of sections. Use care to coordinate section and sort updates, as described in [Configuration](../SectionedFetchRequest/Configuration.zh-Hans.md).

## Configuring the associated sectioned fetch request

- **nsPredicate**: The request’s predicate.
- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.
- **SectionedFetchResults.Section**: A collection of fetched results that share a specified identifier.

