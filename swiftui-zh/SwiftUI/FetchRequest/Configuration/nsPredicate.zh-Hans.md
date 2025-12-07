--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/Configuration/nsPredicate

抓取时间：2025-12-03T10:01:17Z

---

# nsPredicate

**实例属性**

请求的谓词。

## 声明

```swift
@MainActor @preconcurrency var nsPredicate: NSPredicate?
```

## 说明

设置此配置值可使 [FetchRequest](../../FetchRequest.zh-Hans.md) 使用新的谓词执行获取操作。

要访问给定请求的 [Configuration](../Configuration.zh-Hans.md) 结构的此值，可以直接访问关联的 [FetchedResults](../../FetchedResults.zh-Hans.md) 实例上的 [nsPredicate](../../FetchedResults/nsPredicate.zh-Hans.md) 属性，也可以通过 [Binding](../../Binding.zh-Hans.md) 访问。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/Configuration/nsPredicate
crawled: 2025-12-03T10:01:17Z
---

# nsPredicate

**Instance Property**

The request’s predicate.

## Declaration

```swift
@MainActor @preconcurrency var nsPredicate: NSPredicate?
```

## Discussion

Set this configuration value to cause a [FetchRequest](../../FetchRequest.zh-Hans.md) to execute a fetch with a new predicate.

Access this value of a [Configuration](../Configuration.zh-Hans.md) structure for a given request by using the [nsPredicate](../../FetchedResults/nsPredicate.zh-Hans.md) property on the associated [FetchedResults](../../FetchedResults.zh-Hans.md) instance, either directly or through a [Binding](../../Binding.zh-Hans.md).

