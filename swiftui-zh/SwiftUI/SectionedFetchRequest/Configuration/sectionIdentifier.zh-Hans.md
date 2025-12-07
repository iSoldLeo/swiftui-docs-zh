---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration/sectionIdentifier
抓取时间： 2025-12-03T10:01:20Z
---

# sectionIdentifier

**实例属性**

请求的部分标识符关键路径。

## 声明

```swift
var sectionIdentifier: KeyPath<Result, SectionIdentifier>
```

## 讨论

设置此配置值可促使[SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) 使用新的区段标识符执行获取。如果不创建新的获取请求，就无法更改段标识符类型。请按照[Configuration](../Configuration.zh-Hans.md) 中的说明小心协调节和排序更新。

通过使用相关[SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) 实例上的[sectionIdentifier](../../SectionedFetchResults/sectionIdentifier.zh-Hans.md) 属性，可以直接或通过[Binding](../../Binding.zh-Hans.md) 访问给定请求的该值。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration/sectionIdentifier
crawled: 2025-12-03T10:01:20Z
---

# sectionIdentifier

**Instance Property**

The request’s section identifier key path.

## Declaration

```swift
var sectionIdentifier: KeyPath<Result, SectionIdentifier>
```

## Discussion

Set this configuration value to cause a [SectionedFetchRequest](../../SectionedFetchRequest.zh-Hans.md) to execute a fetch with a new section identifier. You can’t change the section identifier type without creating a new fetch request. Use care to coordinate section and sort updates, as described in [Configuration](../Configuration.zh-Hans.md).

Access this value for a given request by using the [sectionIdentifier](../../SectionedFetchResults/sectionIdentifier.zh-Hans.md) property on the associated [SectionedFetchResults](../../SectionedFetchResults.zh-Hans.md) instance, either directly or with a [Binding](../../Binding.zh-Hans.md).

