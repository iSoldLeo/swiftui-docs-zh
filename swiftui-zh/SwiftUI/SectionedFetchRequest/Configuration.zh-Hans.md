---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration
抓取时间： 2025-12-02T18:48:28Z
---

# SectionedFetchRequest.Configuration

**Structure**

请求的可配置属性。

## 声明

```swift
struct Configuration
```

## 概览

您可以通过显式或配置的[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md)，使用部分标识符、可选谓词和排序描述符初始化[doc://com.apple.documentation/documentation/CoreData/NSFetchRequest]。之后，可以使用请求的配置结构动态更新标识符、谓词和排序参数。

您可以通过关联的[SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) 实例上的属性访问或绑定到请求的配置组件，就像使用[FetchRequest](../FetchRequest.zh-Hans.md) 访问[Configuration](../FetchRequest/Configuration.zh-Hans.md) 一样。

配置分段获取请求时，确保分段标识符和主排序描述符的组合不会创建不连续的分段。

## 设置分段标识符

- **sectionIdentifier**：请求的分段标识符关键路径。

## 设置谓词

- **nsPredicate**：请求的谓词。

## 设置排序描述符

- **sortDescriptors**：请求的排序描述符，以值类型访问。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。

## 动态配置请求

- **projectedValue**：与请求的可变配置属性绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/Configuration
crawled: 2025-12-02T18:48:28Z
---

# SectionedFetchRequest.Configuration

**Structure**

The request’s configurable properties.

## Declaration

```swift
struct Configuration
```

## Overview

You initialize a [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) with a section identifier, an optional predicate, and sort descriptors, either explicitly or with a configured [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest]. Later, you can dynamically update the identifier, predicate, and sort parameters using the request’s configuration structure.

You access or bind to a request’s configuration components through properties on the associated [SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) instance, just like you do for a [FetchRequest](../FetchRequest.zh-Hans.md) using [Configuration](../FetchRequest/Configuration.zh-Hans.md).

When configuring a sectioned fetch request, ensure that the combination of the section identifier and the primary sort descriptor doesn’t create discontiguous sections.

## Setting the section identifier

- **sectionIdentifier**: The request’s section identifier key path.

## Setting a predicate

- **nsPredicate**: The request’s predicate.

## Setting sort descriptors

- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.

## Configuring a request dynamically

- **projectedValue**: A binding to the request’s mutable configuration properties.

