---
来源： https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/wrappedValue
抓取时间： 2025-12-02T18:48:30Z
---

# wrappedValue

**实例属性**

获取请求的提取结果。

## 声明

```swift
@MainActor @preconcurrency var wrappedValue: SectionedFetchResults<SectionIdentifier, Result> { get }
```

## 讨论

此属性的行为类似于[wrappedValue](../FetchRequest/wrappedValue.zh-Hans.md) 的[FetchRequest](../FetchRequest.zh-Hans.md)。特别是，当您将[SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) 用作属性包装器，然后通过名称访问被包装的属性时，SwiftUI 会返回与该属性相关联的值。例如，请看下面的`quakes` 属性声明，它获取了`Quake` 类型，该类型由[doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] 示例代码项目定义：

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

您可以通过引用`quakes` 属性的名称来访问请求的`wrappedValue`，其中包含一个[SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) 实例。该值是一个部分集合，每个部分包含一组托管对象：

```swift
Text("Found \(quakes.count) days of earthquakes")
```

如果需要将请求和结果实体分开，可以分两步声明`quakes`，使用请求的`wrappedValue` 来获取结果：

```swift
var fetchRequest = SectionedFetchRequest<String, Quake>(
    fetchRequest: request,
    sectionIdentifier: \.day)
var quakes: SectionedFetchedResults<String, Quake> { fetchRequest.wrappedValue }
```

当没有获取结果时，`wrappedValue` 属性会返回一个空数组；例如，因为没有实体满足谓词，或者因为数据存储为空。

## 获取获取的结果

- **update()**：更新获取的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/SectionedFetchRequest/wrappedValue
crawled: 2025-12-02T18:48:30Z
---

# wrappedValue

**Instance Property**

The fetched results of the fetch request.

## Declaration

```swift
@MainActor @preconcurrency var wrappedValue: SectionedFetchResults<SectionIdentifier, Result> { get }
```

## Discussion

This property behaves like the [wrappedValue](../FetchRequest/wrappedValue.zh-Hans.md) of a [FetchRequest](../FetchRequest.zh-Hans.md). In particular, SwiftUI returns the value associated with this property when you use [SectionedFetchRequest](../SectionedFetchRequest.zh-Hans.md) as a property wrapper and then access the wrapped property by name. For example, consider the following `quakes` property declaration that fetches a `Quake` type that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines:

```swift
@SectionedFetchRequest<String, Quake>(
    sectionIdentifier: \.day,
    sortDescriptors: [SortDescriptor(\.time, order: .reverse)]
)
private var quakes: SectionedFetchResults<String, Quake>
```

You access the request’s `wrappedValue`, which contains a [SectionedFetchResults](../SectionedFetchResults.zh-Hans.md) instance, by referring to the `quakes` property by name. That value is a collection of sections, each of which contains a group of managed objects:

```swift
Text("Found \(quakes.count) days of earthquakes")
```

If you need to separate the request and the result entities, you can declare `quakes` in two steps by using the request’s `wrappedValue` to obtain the results:

```swift
var fetchRequest = SectionedFetchRequest<String, Quake>(
    fetchRequest: request,
    sectionIdentifier: \.day)
var quakes: SectionedFetchedResults<String, Quake> { fetchRequest.wrappedValue }
```

The `wrappedValue` property returns an empty array when there are no fetched results; for example, because no entities satisfy the predicate, or because the data store is empty.

## Getting the fetched results

- **update()**: Updates the fetched results.

