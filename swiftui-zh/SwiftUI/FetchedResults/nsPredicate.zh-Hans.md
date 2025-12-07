---
来源： https://developer.apple.com/documentation/SwiftUI/FetchedResults/nsPredicate
抓取时间： 2025-12-02T18:48:20Z
---

# nsPredicate

**实例属性**

请求的谓词。

## 声明

```swift
@MainActor @preconcurrency var nsPredicate: NSPredicate? { get nonmutating set }
```

## 讨论

设置此值后，相关的[FetchRequest](../FetchRequest.zh-Hans.md) 将使用新的谓词执行获取操作，生成更新的结果集合。

## 配置关联的提取请求

- **sortDescriptors**：请求的排序描述符，作为值类型访问。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchedResults/nsPredicate
crawled: 2025-12-02T18:48:20Z
---

# nsPredicate

**Instance Property**

The request’s predicate.

## Declaration

```swift
@MainActor @preconcurrency var nsPredicate: NSPredicate? { get nonmutating set }
```

## Discussion

Set this value to cause the associated [FetchRequest](../FetchRequest.zh-Hans.md) to execute a fetch with a new predicate, producing an updated collection of results.

## Configuring the associated fetch request

- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.

