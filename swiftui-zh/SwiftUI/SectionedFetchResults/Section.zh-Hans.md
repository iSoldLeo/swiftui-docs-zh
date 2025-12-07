---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/Section
抓取时间： 2025-12-02T18:48:40Z
---

# SectionedFetchResults.Section

**Structure**

共享指定标识符的提取结果集合。

## 声明

```swift
@MainActor @preconcurrency struct Section
```

## 概览

检查`Section` 实例以查找满足[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) 谓词的实体，这些实体的特定属性值存储在该部分的[id](Section/id.zh-Hans.md) 参数中。您可以通过在初始化过程中设置取回请求的`sectionIdentifier` 参数，或通过修改相应[SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) 实例的[sectionIdentifier](sectionIdentifier.zh-Hans.md) 属性来指定哪个属性。

通过将获取结果视为一个集合来获取特定部分。例如，请看下面的属性声明，该声明用于获取`Quake` 托管对象，该托管对象由 [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] 示例代码项目定义，用于存储地震数据：

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

使用下标获取第一节：

```swift
let firstSection = quakes[0]
```

或者，您也可以循环查看章节，创建章节列表。

```swift
ForEach(quakes) { section in
    Text("Section \(section.id) has \(section.count) elements")
}
```

小节也可以作为集合使用，这意味着你可以使用像上例中的[doc://com.apple.documentation/documentation/Swift/Collection/count-4l4qk] 属性这样的元素。

## 标识部分

- **id**：部分中所有实体共享的指定关键路径的值。

## 获取索引

- **startIndex**：部分中第一个实体的索引。
- **endIndex**：比区段中最后一个实体的索引大一个的索引。

## 获取结果

- **subscript(_:)**：获取部分中指定索引处的实体。

## 配置相关的分段获取请求

- **nsPredicate**：请求的谓词。
- **sortDescriptors**：请求的排序描述符，作为值类型访问。
- **nsSortDescriptors**：请求的排序描述符，作为引用类型访问。
- **sectionIdentifier**：系统用于将获取的结果分组的关键路径。

## 符合

- 双向集合
- 集合
- 可识别
- 随机访问集合
- 可发送
- 可发送元类型
- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchResults/Section
crawled: 2025-12-02T18:48:40Z
---

# SectionedFetchResults.Section

**Structure**

A collection of fetched results that share a specified identifier.

## Declaration

```swift
@MainActor @preconcurrency struct Section
```

## Overview

Examine a `Section` instance to find the entities that satisfy a [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) predicate, and that have a particular property with the value stored in the section’s [id](Section/id.zh-Hans.md) parameter. You specify which property by setting the fetch request’s `sectionIdentifier` parameter during initialization, or by modifying the corresponding [SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) instance’s [sectionIdentifier](sectionIdentifier.zh-Hans.md) property.

Obtain specific sections by treating the fetch results as a collection. For example, consider the following property declaration that fetches `Quake` managed objects that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines to store earthquake data:

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

Get the first section using a subscript:

```swift
let firstSection = quakes[0]
```

Alternatively, you can loop over the sections to create a list of sections.

```swift
ForEach(quakes) { section in
    Text("Section \(section.id) has \(section.count) elements")
}
```

The sections also act as collections, which means you can use elements like the [doc://com.apple.documentation/documentation/Swift/Collection/count-4l4qk] property in the example above.

## Identifying the section

- **id**: The value that all entities in the section share for a specified key path.

## Getting indices

- **startIndex**: The index of the first entity in the section.
- **endIndex**: The index that’s one greater than that of the last entity in the section.

## Getting results

- **subscript(_:)**: Gets the entity at the specified index within the section.

## Configuring the associated sectioned fetch request

- **nsPredicate**: The request’s predicate.
- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.
- **sectionIdentifier**: The key path that the system uses to group fetched results into sections.

## Conforms To

- BidirectionalCollection
- Collection
- Identifiable
- RandomAccessCollection
- Sendable
- SendableMetatype
- Sequence

