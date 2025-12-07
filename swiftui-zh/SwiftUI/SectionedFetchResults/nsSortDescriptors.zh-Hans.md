---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/nsSortDescriptors
抓取时间： 2025-12-02T18:48:39Z
---

# nsSortDescriptors

**实例属性**

请求的排序描述符，作为引用类型访问。

## 声明

```swift
@MainActor @preconcurrency var nsSortDescriptors: [NSSortDescriptor] { get nonmutating set }
```

## 讨论

设置此值可使关联的[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) 使用新的[doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] 实例集合执行获取。结果集合中存储的托管对象的顺序可能会因此改变。请按照[Configuration](../SectionedFetchRequest/Configuration.zh-Hans.md) 中的说明，小心协调分段和排序更新。

如果要使用 [doc://com.apple.documentation/documentation/Foundation/SortDescriptor] 实例，请设置 [sortDescriptors](sortDescriptors.zh-Hans.md) 代替。

## 配置相关的分段获取请求

- **nsPredicate**：请求的谓词。
- **sortDescriptors**：请求的排序描述符，作为值类型访问。
- **sectionIdentifier**：系统用于将获取的结果分组的关键路径。
- **SectionedFetchResults.Section**：共享指定标识符的提取结果集合。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/nsSortDescriptors
crawled: 2025-12-02T18:48:39Z
---

# nsSortDescriptors

**Instance Property**

The request’s sort descriptors, accessed as reference types.

## Declaration

```swift
@MainActor @preconcurrency var nsSortDescriptors: [NSSortDescriptor] { get nonmutating set }
```

## Discussion

Set this value to cause the associated [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) to execute a fetch with a new collection of [doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] instances. The order of managed objects stored in the results collection may change as a result. Use care to coordinate section and sort updates, as described in [Configuration](../SectionedFetchRequest/Configuration.zh-Hans.md).

If you want to use [doc://com.apple.documentation/documentation/Foundation/SortDescriptor] instances, set [sortDescriptors](sortDescriptors.zh-Hans.md) instead.

## Configuring the associated sectioned fetch request

- **nsPredicate**: The request’s predicate.
- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **sectionIdentifier**: The key path that the system uses to group fetched results into sections.
- **SectionedFetchResults.Section**: A collection of fetched results that share a specified identifier.

