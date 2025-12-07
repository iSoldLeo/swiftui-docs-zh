--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/projectedValue
抓取时间：2025-12-02T18:48:11Z

---

# projectedValue

**实例属性**

绑定到请求的可变配置属性。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: Binding<FetchRequest<Result>.Configuration> { get }
```

## 讨论

当您使用 [FetchRequest](../FetchRequest.zh-Hans.md) 作为 [FetchedResults](../FetchedResults.zh-Hans.md) 实例的属性包装器，然后使用美元符号 (`$`) 前缀访问结果时，SwiftUI 会返回与此属性关联的值。SwiftUI 返回的值是 [Binding](../Binding.zh-Hans.md) 到请求的 [Configuration](Configuration.zh-Hans.md) 结构的映射，该结构用于动态配置请求。

例如，考虑以下获取请求，该请求针对的是 [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] 示例代码项目定义的用于存储地震数据的类型，并根据 `time` 属性进行排序：

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake>
```

您可以使用投影值来启用 [Table](../Table.zh-Hans.md) 实例进行更新：

```swift
Table(quakes, sortOrder: $quakes.sortDescriptors) {
    TableColumn("Place", value: \.place)
    TableColumn("Time", value: \.time) { quake in
        Text(quake.time, style: .time)
    }
}
```

由于您使用绑定到描述符来初始化表，因此该表可以根据用户执行的操作（例如单击列标题）来修改排序。

## 动态配置请求

- **FetchRequest.Configuration**：请求的可配置属性。


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/projectedValue
crawled: 2025-12-02T18:48:11Z
---

# projectedValue

**Instance Property**

A binding to the request’s mutable configuration properties.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: Binding<FetchRequest<Result>.Configuration> { get }
```

## Discussion

SwiftUI returns the value associated with this property when you use [FetchRequest](../FetchRequest.zh-Hans.md) as a property wrapper on a [FetchedResults](../FetchedResults.zh-Hans.md) instance, and then access the results with a dollar sign (`$`) prefix. The value that SwiftUI returns is a [Binding](../Binding.zh-Hans.md) to the request’s [Configuration](Configuration.zh-Hans.md) structure, which dynamically configures the request.

For example, consider the following fetch request for a type that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines to store earthquake data, sorted based on the `time` property:

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake>
```

You can use the projected value to enable a [Table](../Table.zh-Hans.md) instance to make updates:

```swift
Table(quakes, sortOrder: $quakes.sortDescriptors) {
    TableColumn("Place", value: \.place)
    TableColumn("Time", value: \.time) { quake in
        Text(quake.time, style: .time)
    }
}
```

Because you initialize the table using a binding to the descriptors, the table can modify the sort in response to actions that the user takes, like clicking a column header.

## Configuring a request dynamically

- **FetchRequest.Configuration**: The request’s configurable properties.

