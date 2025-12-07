---
来源： https://developer.apple.com/documentation/SwiftUI/FetchedResults/sortDescriptors
抓取时间： 2025-12-02T18:48:20Z
---

# 排序描述符

**实例属性**

请求的排序描述符，以值类型访问。

## 声明

```swift
@MainActor @preconcurrency var sortDescriptors: [SortDescriptor<Result>] { get nonmutating set }
```

## 讨论

设置此值可使关联的[FetchRequest](../FetchRequest.zh-Hans.md) 使用新的[doc://com.apple.documentation/documentation/Foundation/SortDescriptor] 实例集合执行获取。结果集合中存储的实体顺序可能会因此改变。

如果要使用[doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] 实例，请设置[nsSortDescriptors](nsSortDescriptors.zh-Hans.md)。

## 配置相关的获取请求

- **nsPredicate**：请求的谓词。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchedResults/sortDescriptors
crawled: 2025-12-02T18:48:20Z
---

# sortDescriptors

**Instance Property**

The request’s sort descriptors, accessed as value types.

## Declaration

```swift
@MainActor @preconcurrency var sortDescriptors: [SortDescriptor<Result>] { get nonmutating set }
```

## Discussion

Set this value to cause the associated [FetchRequest](../FetchRequest.zh-Hans.md) to execute a fetch with a new collection of [doc://com.apple.documentation/documentation/Foundation/SortDescriptor] instances. The order of entities stored in the results collection may change as a result.

If you want to use [doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] instances, set [nsSortDescriptors](nsSortDescriptors.zh-Hans.md) instead.

## Configuring the associated fetch request

- **nsPredicate**: The request’s predicate.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.

