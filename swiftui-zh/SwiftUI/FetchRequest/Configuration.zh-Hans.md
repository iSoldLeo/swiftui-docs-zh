--- 来源：https://developer.apple.com/documentation/SwiftUI/FetchRequest/Configuration
抓取时间：2025-12-02T18:48:11Z
---

# FetchRequest.Configuration

**Structure**

请求的可配置属性。

## 声明

```swift
@MainActor @preconcurrency struct Configuration
```

## 概述

您可以使用可选的谓词和排序描述符初始化 [FetchRequest](../FetchRequest.zh-Hans.md)，可以显式初始化，也可以使用已配置的 [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest]。之后，您可以使用请求的配置结构动态更新谓词和排序参数。

您可以通过关联的 [FetchedResults](../FetchedResults.zh-Hans.md) 实例上的属性访问或绑定请求的配置组件。

### 使用绑定进行配置

要获取获取请求的配置结构，需要访问请求的 [projectedValue](projectedValue.zh-Hans.md)，方法是在关联的结果属性上使用美元符号 (`$`) 前缀。例如，您可以创建一个针对 `Quake` 实体的请求——这是一个托管对象类型，由 [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] 示例代码项目定义——该请求最初按时间对结果进行排序：

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake>
```

然后，您可以将请求的排序描述符（可通过 `quakes` 结果访问）绑定到 [Table](../Table.zh-Hans.md) 实例的排序描述符：

```swift
Table(quakes, sortOrder: $quakes.sortDescriptors) {
    TableColumn("Place", value: \.place)
    TableColumn("Time", value: \.time) { quake in
        Text(quake.time, style: .time)
    }
}
```

用户点击表格列标题会触发以下事件序列：

1. 表格通过绑定更新排序描述符。

2. 修改后的排序描述符重新配置请求。

3. 重新配置的请求获取新结果。

4. SwiftUI 根据新结果重新绘制表格。

### 直接设置配置

如果需要直接访问获取请求的配置元素，请使用 [FetchedResults](../FetchedResults.zh-Hans.md) 实例的 [nsPredicate](../FetchedResults/nsPredicate.zh-Hans.md) 和 [sortDescriptors](../FetchedResults/sortDescriptors.zh-Hans.md) 或 [nsSortDescriptors](../FetchedResults/nsSortDescriptors.zh-Hans.md) 属性。继续上面的例子，为了使用户能够动态更新谓词，请声明一个 [State](../State.zh-Hans.md) 属性来保存查询字符串：

```swift
@State private var query = ""
```

然后，向 [Table](../Table.zh-Hans.md) 添加一个 [onChange(of:initial:_:)](../View/onChange_of_initial.zh-Hans.md) 修饰符，以便在查询发生更改时设置新的谓词：

```swift
.onChange(of: query) { _, value in
    quakes.nsPredicate = query.isEmpty
        ? nil
        : NSPredicate(format: "place CONTAINS %@", value)
}
```

为了让用户能够控制字符串，请在用户界面中添加一个绑定到 `query` 状态的 [TextField](../TextField.zh-Hans.md)：

```swift
TextField("Filter", text: $query)
```

当用户在文本字段中输入内容时，谓词会更新，请求会获取新的结果，SwiftUI 会重新绘制表格。

## 设置谓词

- **nsPredicate**：请求的谓词。

## 设置排序描述符

- **sortDescriptors**：请求的排序描述符，以值类型访问。

- **nsSortDescriptors**：请求的排序描述符，以引用类型访问。

## 动态配置请求

- **projectedValue**：绑定到请求的可变配置属性。

## 符合以下协议：

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/FetchRequest/Configuration
crawled: 2025-12-02T18:48:11Z
---

# FetchRequest.Configuration

**Structure**

The request’s configurable properties.

## Declaration

```swift
@MainActor @preconcurrency struct Configuration
```

## Overview

You initialize a [FetchRequest](../FetchRequest.zh-Hans.md) with an optional predicate and sort descriptors, either explicitly or using a configured [doc://com.apple.documentation/documentation/CoreData/NSFetchRequest]. Later, you can dynamically update the predicate and sort parameters using the request’s configuration structure.

You access or bind to a request’s configuration components through properties on the associated [FetchedResults](../FetchedResults.zh-Hans.md) instance.

### Configure using a binding

Get a [Binding](../Binding.zh-Hans.md) to a fetch request’s configuration structure by accessing the request’s [projectedValue](projectedValue.zh-Hans.md), which you do by using the dollar sign (`$`) prefix on the associated results property. For example, you can create a request for `Quake` entities — a managed object type that the [doc://com.apple.documentation/documentation/swiftui/loading_and_displaying_a_large_data_feed] sample code project defines — that initially sorts the results by time:

```swift
@FetchRequest(sortDescriptors: [SortDescriptor(\.time, order: .reverse)])
private var quakes: FetchedResults<Quake>
```

Then you can bind the request’s sort descriptors, which you access through the `quakes` result, to those of a [Table](../Table.zh-Hans.md) instance:

```swift
Table(quakes, sortOrder: $quakes.sortDescriptors) {
    TableColumn("Place", value: \.place)
    TableColumn("Time", value: \.time) { quake in
        Text(quake.time, style: .time)
    }
}
```

A user who clicks on a table column header initiates the following sequence of events:

1. The table updates the sort descriptors through the binding.
2. The modified sort descriptors reconfigure the request.
3. The reconfigured request fetches new results.
4. SwiftUI redraws the table in response to new results.

### Set configuration directly

If you need to access the fetch request’s configuration elements directly, use the [nsPredicate](../FetchedResults/nsPredicate.zh-Hans.md) and [sortDescriptors](../FetchedResults/sortDescriptors.zh-Hans.md) or [nsSortDescriptors](../FetchedResults/nsSortDescriptors.zh-Hans.md) properties of the [FetchedResults](../FetchedResults.zh-Hans.md) instance. Continuing the example above, to enable the user to dynamically update the predicate, declare a [State](../State.zh-Hans.md) property to hold a query string:

```swift
@State private var query = ""
```

Then add an [onChange(of:initial:_:)](../View/onChange_of_initial.zh-Hans.md) modifier to the [Table](../Table.zh-Hans.md) that sets a new predicate any time the query changes:

```swift
.onChange(of: query) { _, value in
    quakes.nsPredicate = query.isEmpty
        ? nil
        : NSPredicate(format: "place CONTAINS %@", value)
}
```

To give the user control over the string, add a [TextField](../TextField.zh-Hans.md) in your user interface that’s bound to the `query` state:

```swift
TextField("Filter", text: $query)
```

When the user types into the text field, the predicate updates, the request fetches new results, and SwiftUI redraws the table.

## Setting a predicate

- **nsPredicate**: The request’s predicate.

## Setting sort descriptors

- **sortDescriptors**: The request’s sort descriptors, accessed as value types.
- **nsSortDescriptors**: The request’s sort descriptors, accessed as reference types.

## Configuring a request dynamically

- **projectedValue**: A binding to the request’s mutable configuration properties.

## Conforms To

- Sendable
- SendableMetatype

