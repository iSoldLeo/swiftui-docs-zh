--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/Configuration/nsSortDescriptors

抓取时间：2025-12-03T10:01:18Z

---

# nsSortDescriptors

**实例属性**

请求的排序描述符，以引用类型访问。

## 声明

```swift
@MainActor @preconcurrency var nsSortDescriptors: [NSSortDescriptor]
```

## 说明

设置此配置值可使 [FetchRequest](../../FetchRequest.zh-Hans.md) 使用新的 [doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] 实例集合执行获取操作。如果要使用 [doc://com.apple.documentation/documentation/Foundation/SortDescriptor] 实例，请改为设置 [sortDescriptors](sortDescriptors.zh-Hans.md)。

要访问给定请求的 [Configuration](../Configuration.zh-Hans.md) 结构的值，可以直接使用关联的 [FetchedResults](../../FetchedResults.zh-Hans.md) 实例上的 [nsSortDescriptors](../../FetchedResults/nsSortDescriptors.zh-Hans.md) 属性，也可以通过 [Binding](../../Binding.zh-Hans.md) 访问。

## 设置排序描述符

- **sortDescriptors**：请求的排序描述符，以值类型访问。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/Configuration/nsSortDescriptors
crawled: 2025-12-03T10:01:18Z
---

# nsSortDescriptors

**Instance Property**

The request’s sort descriptors, accessed as reference types.

## Declaration

```swift
@MainActor @preconcurrency var nsSortDescriptors: [NSSortDescriptor]
```

## Discussion

Set this configuration value to cause a [FetchRequest](../../FetchRequest.zh-Hans.md) to execute a fetch with a new collection of [doc://com.apple.documentation/documentation/Foundation/NSSortDescriptor] instances. If you want to use [doc://com.apple.documentation/documentation/Foundation/SortDescriptor] instances, set [sortDescriptors](sortDescriptors.zh-Hans.md) instead.

Access this value of a [Configuration](../Configuration.zh-Hans.md) structure for a given request by using the [nsSortDescriptors](../../FetchedResults/nsSortDescriptors.zh-Hans.md) property on the associated [FetchedResults](../../FetchedResults.zh-Hans.md) instance, either directly or through a [Binding](../../Binding.zh-Hans.md).

## Setting sort descriptors

- **sortDescriptors**: The request’s sort descriptors, accessed as value types.

