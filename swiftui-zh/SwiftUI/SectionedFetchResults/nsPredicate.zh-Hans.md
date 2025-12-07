---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/nsPredicate
抓取时间： 2025-12-02T18:48:37Z
---

# nsPredicate

**实例属性**

请求的谓词。

## 声明

```swift
@MainActor @preconcurrency var nsPredicate: NSPredicate? { get nonmutating set }
```

## 讨论

设置此值后，相关的[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) 将使用新的谓词执行获取操作，生成更新的结果集合。

## 配置关联的分段提取请求

- **sortDescriptors**：请求的排序描述符，作为值类型访问。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。
- **sectionIdentifier**：系统用于将获取的结果分组的关键路径。
- **SectionedFetchResults.Section**：共享指定标识符的提取结果集合。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/nsPredicate
crawled: 2025-12-02T18:48:37Z
---

# nsPredicate

**Instance Property**

The request’s predicate.

## Declaration

```swift
@MainActor @preconcurrency var nsPredicate: NSPredicate? { get nonmutating set }
```

## Discussion

Set this value to cause the associated [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) to execute a fetch with a new predicate, producing an updated collection of results.

## Configuring the associated sectioned fetch request

- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.
- **sectionIdentifier**: The key path that the system uses to group fetched results into sections.
- **SectionedFetchResults.Section**: A collection of fetched results that share a specified identifier.

