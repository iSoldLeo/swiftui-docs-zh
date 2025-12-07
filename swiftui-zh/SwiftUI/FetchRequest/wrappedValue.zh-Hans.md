--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/wrappedValue
抓取时间：2025-12-02T18:48:13Z

---

# wrappedValue

**实例属性**

获取请求的结果。

## 声明

```swift
@MainActor @preconcurrency var wrappedValue: FetchedResults<Result> { get }
```

## 讨论

当您使用 [FetchRequest](../FetchRequest.zh-Hans.md) 作为属性包装器，然后通过名称访问被包装的属性时，SwiftUI 会返回与此属性关联的值。例如，考虑以下属性声明 `quakes`，它获取示例代码项目 [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] 定义的 `Quake` 类型：

```swift
@FetchRequest(fetchRequest: request)
private var quakes: FetchedResults<Quake>
```

您可以通过引用属性名称 `quakes` 来访问请求的 `wrappedValue`，其中包含一个 [FetchedResults](../FetchedResults.zh-Hans.md) 实例：

```swift
Text("Found \(quakes.count) earthquakes")
```

如果您需要将请求实体和结果实体分开，可以使用请求的 `wrappedValue` 分两步声明 `quakes` 以获取结果：

```swift
var fetchRequest = FetchRequest<Quake>(fetchRequest: request)
var quakes: FetchedResults<Quake> { fetchRequest.wrappedValue }
```

当没有结果时，属性 `wrappedValue` 返回一个空数组。获取到的结果——例如，因为没有实体满足谓词，或者因为数据存储为空。

## 获取已获取的结果

- **update()**：更新已获取的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/wrappedValue
crawled: 2025-12-02T18:48:13Z
---

# wrappedValue

**Instance Property**

The fetched results of the fetch request.

## Declaration

```swift
@MainActor @preconcurrency var wrappedValue: FetchedResults<Result> { get }
```

## Discussion

SwiftUI returns the value associated with this property when you use [FetchRequest](../FetchRequest.zh-Hans.md) as a property wrapper, and then access the wrapped property by name. For example, consider the following `quakes` property declaration that fetches a `Quake` type that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines:

```swift
@FetchRequest(fetchRequest: request)
private var quakes: FetchedResults<Quake>
```

You access the request’s `wrappedValue`, which contains a [FetchedResults](../FetchedResults.zh-Hans.md) instance, by referring to the `quakes` property by name:

```swift
Text("Found \(quakes.count) earthquakes")
```

If you need to separate the request and the result entities, you can declare `quakes` in two steps by using the request’s `wrappedValue` to obtain the results:

```swift
var fetchRequest = FetchRequest<Quake>(fetchRequest: request)
var quakes: FetchedResults<Quake> { fetchRequest.wrappedValue }
```

The `wrappedValue` property returns an empty array when there are no fetched results — for example, because no entities satisfy the predicate, or because the data store is empty.

## Getting the fetched results

- **update()**: Updates the fetched results.

