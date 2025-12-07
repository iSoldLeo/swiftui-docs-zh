---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/projectedValue
抓取时间： 2025-12-02T18:48:29Z
---

# 预计值

**实例属性**

与请求的可变配置属性绑定。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: Binding<SectionedFetchRequest<SectionIdentifier, Result>.Configuration> { get }
```

## 讨论

该属性的行为类似于[projectedValue](../FetchRequest/projectedValue.zh-Hans.md) 的[FetchRequest](../FetchRequest.zh-Hans.md)。特别是，当您使用[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) 作为[SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) 实例的属性包装器，然后使用美元符号 (`$`) 前缀访问结果时，SwiftUI 会返回与此属性相关的值。SwiftUI 返回的值是请求的[Binding](../Binding.zh-Hans.md) 结构的[Configuration](Configuration.zh-Hans.md)，该结构可动态配置请求。

## 动态配置请求

- **SectionedFetchRequest.Configuration**：请求的可配置属性。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/projectedValue
crawled: 2025-12-02T18:48:29Z
---

# projectedValue

**Instance Property**

A binding to the request’s mutable configuration properties.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: Binding<SectionedFetchRequest<SectionIdentifier, Result>.Configuration> { get }
```

## Discussion

This property behaves like the [projectedValue](../FetchRequest/projectedValue.zh-Hans.md) of a [FetchRequest](../FetchRequest.zh-Hans.md). In particular, SwiftUI returns the value associated with this property when you use [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) as a property wrapper on a [SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) instance and then access the results with a dollar sign (`$`) prefix. The value that SwiftUI returns is a [Binding](../Binding.zh-Hans.md) to the request’s [Configuration](Configuration.zh-Hans.md) structure, which dynamically configures the request.

## Configuring a request dynamically

- **SectionedFetchRequest.Configuration**: The request’s configurable properties.

