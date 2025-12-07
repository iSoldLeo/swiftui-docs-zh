---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration/nsSortDescriptors
抓取时间： 2025-12-03T10:01:22Z
---

# nsSortDescriptors

**实例属性**

请求的排序描述符，作为引用类型访问。

## 声明

```swift
var nsSortDescriptors: [NSSortDescriptor]
```

## 讨论

设置此配置值可促使[SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) 使用新的[doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] 实例集合执行获取。如果要使用[doc://com.apple.documentation/documentation/Foundation/SortDescriptor] 实例，请设置[sortDescriptors](sortDescriptors.zh-Hans.md)。请按照[Configuration](../Configuration.zh-Hans.md) 中的说明，小心协调章节和排序更新。

通过使用相关[SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) 实例上的[nsSortDescriptors](../../SectionedFetchResults/nsSortDescriptors.zh-Hans.md) 属性，可以直接或通过[Binding](../../Binding.zh-Hans.md) 访问给定请求的该值。

## 设置排序描述符

- **sortDescriptors**：请求的排序描述符，以值类型访问。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration/nsSortDescriptors
crawled: 2025-12-03T10:01:22Z
---

# nsSortDescriptors

**Instance Property**

The request’s sort descriptors, accessed as reference types.

## Declaration

```swift
var nsSortDescriptors: [NSSortDescriptor]
```

## Discussion

Set this configuration value to cause a [SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) to execute a fetch with a new collection of [doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] instances. If you want to use [doc://com.apple.documentation/documentation/Foundation/SortDescriptor] instances, set [sortDescriptors](sortDescriptors.zh-Hans.md) instead. Use care to coordinate section and sort updates, as described in [Configuration](../Configuration.zh-Hans.md).

Access this value for a given request by using the [nsSortDescriptors](../../SectionedFetchResults/nsSortDescriptors.zh-Hans.md) property on the associated [SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) instance, either directly or with a [Binding](../../Binding.zh-Hans.md).

## Setting sort descriptors

- **sortDescriptors**: The request’s sort descriptors, accessed as value types.

