---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration/nsPredicate
抓取时间： 2025-12-03T10:01:21Z
---

# nsPredicate

**实例属性**

请求的谓词。

## 声明

```swift
var nsPredicate: NSPredicate?
```

## 讨论

设置此配置值可促使[SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) 执行带有新谓词的获取。

通过使用相关[SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) 实例上的[nsPredicate](../../SectionedFetchResults/nsPredicate.zh-Hans.md) 属性，可以直接或通过[Binding](../../Binding.zh-Hans.md) 访问给定请求的该值。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration/nsPredicate
crawled: 2025-12-03T10:01:21Z
---

# nsPredicate

**Instance Property**

The request’s predicate.

## Declaration

```swift
var nsPredicate: NSPredicate?
```

## Discussion

Set this configuration value to cause a [SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) to execute a fetch with a new predicate.

Access this value for a given request by using the [nsPredicate](../../SectionedFetchResults/nsPredicate.zh-Hans.md) property on the associated [SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) instance, either directly or with a [Binding](../../Binding.zh-Hans.md).

