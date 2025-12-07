--- 来源：https://developer.apple.com/documentation/SwiftUI/ForEach
抓取时间：2025-12-02T17:27:03Z

---

# ForEach

**Structure**

一种结构，可根据底层已识别数据集合按需计算视图。

## 声明

```swift
struct ForEach<Data, ID, Content> where Data : RandomAccessCollection, ID : Hashable
```

## 概述

使用 `ForEach` 基于某种数据类型的 [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] 提供视图。集合的元素必须符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 规范，或者需要向 `id` 初始化器提供参数。

以下示例创建了一个符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 规范的 `NamedFont` 类型，以及一个名为 `namedFonts` 的该类型数组。一个 `ForEach` 实例遍历该数组，生成新的 [Text](Text.zh-Hans.md) 实例，用于显示数组中提供的每个 SwiftUI [Font](Font.zh-Hans.md) 样式的示例。

```swift
private struct NamedFont: Identifiable {
    let name: String
    let font: Font
    var id: String { name }
}

private let namedFonts: [NamedFont] = [
    NamedFont(name: "Large Title", font: .largeTitle),
    NamedFont(name: "Title", font: .title),
    NamedFont(name: "Headline", font: .headline),
    NamedFont(name: "Body", font: .body),
    NamedFont(name: "Caption", font: .caption)
]

var body: some View {
    ForEach(namedFonts) { namedFont in
        Text(namedFont.name)
            .font(namedFont.font)
    }
}
```

某些容器（例如 [List](List.zh-Hans.md) 或 [LazyVStack](LazyVStack.zh-Hans.md)）会延迟查询其中的元素。为了获得最佳性能，请确保从集合中的每个元素创建的视图代表固定数量的视图。

例如，以下视图使用 if 语句，这意味着集合中的每个元素可以代表 1 个或 0 个视图，这是一个非固定值。 ```swift
ForEach(namedFonts) { namedFont in
    if namedFont.name.count != 2 {
        Text(namedFont.name)
    }
}
```

您可以通过将条件包装在 [VStack](VStack.zh-Hans.md)、[HStack](HStack.zh-Hans.md) 或 [ZStack](ZStack.zh-Hans.md) 中，使上述视图表示固定数量的视图。

```swift
ForEach(namedFonts) { namedFont in
    VStack {
        if namedFont.name.count != 2 {
            Text(namedFont.name)
        }
    }
}
```

启用以下启动参数后，SwiftUI 将在遇到在这些容器中生成非固定数量视图的视图时记录日志：

```swift
-LogForEachSlowPath YES
```

## 创建集合

- **init(_:)**：创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建表行。

- **init(_:content:)**：创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建地图内容。

- **init(_:id:content:)**：创建一个实例，该实例基于提供的指向底层数据标识符的键路径，在更新过程中唯一标识并创建映射内容。

## 创建可编辑集合

- **init(_:editActions:content:)**：创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建视图。

- **init(_:id:editActions:content:)**：创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建视图。

## 访问内容

- **content**：一个使用底层数据按需创建内容的函数。

- **data**：SwiftUI 用于动态创建视图的底层标识数据集合。

## 初始化器

- **init(sections:content:)**：创建一个实例，该实例能够唯一标识并根据给定视图的各个部分在更新过程中创建视图。

- **init(subviews:content:)**：创建一个实例，该实例能够唯一标识并根据给定视图的子视图在更新过程中创建视图。

## 遍历动态数据

- **ForEachSectionCollection**：一个集合，允许在 for each 循环中将视图视为其各个部分的集合。

- **ForEachSubviewCollection**：一个集合，允许在 for each 循环中将视图视为其子视图的集合。

- **DynamicViewContent**：一种视图类型，它能够从底层数据集合生成视图。

## 符合以下规范

- AccessibilityRotorContent

- AttachmentContent

- Chart3DContent

- ChartContent

- Copyable

- DynamicMapContent

- DynamicTableRowContent

- DynamicViewContent

- MapContent

- TabContent

- TableRowContent

- View


---
source: https://developer.apple.com/documentation/SwiftUI/ForEach
crawled: 2025-12-02T17:27:03Z
---

# ForEach

**Structure**

A structure that computes views on demand from an underlying collection of identified data.

## Declaration

```swift
struct ForEach<Data, ID, Content> where Data : RandomAccessCollection, ID : Hashable
```

## Overview

Use `ForEach` to provide views based on a [doc://com.apple.documentation/documentation/Swift/RandomAccessCollection] of some data type. Either the collection’s elements must conform to [doc://com.apple.documentation/documentation/Swift/Identifiable] or you need to provide an `id` parameter to the `ForEach` initializer.

The following example creates a `NamedFont` type that conforms to [doc://com.apple.documentation/documentation/Swift/Identifiable], and an array of this type called `namedFonts`. A `ForEach` instance iterates over the array, producing new [Text](Text.zh-Hans.md) instances that display examples of each SwiftUI [Font](Font.zh-Hans.md) style provided in the array.

```swift
private struct NamedFont: Identifiable {
    let name: String
    let font: Font
    var id: String { name }
}

private let namedFonts: [NamedFont] = [
    NamedFont(name: "Large Title", font: .largeTitle),
    NamedFont(name: "Title", font: .title),
    NamedFont(name: "Headline", font: .headline),
    NamedFont(name: "Body", font: .body),
    NamedFont(name: "Caption", font: .caption)
]

var body: some View {
    ForEach(namedFonts) { namedFont in
        Text(namedFont.name)
            .font(namedFont.font)
    }
}
```



Some containers like [List](List.zh-Hans.md) or [LazyVStack](LazyVStack.zh-Hans.md) will query the elements within a for each lazily. To obtain maximal performance, ensure that the view created from each element in the collection represents a constant number of views.

For example, the following view uses an if statement which means each element of the collection can represent either 1 or 0 views, a non-constant number.

```swift
ForEach(namedFonts) { namedFont in
    if namedFont.name.count != 2 {
        Text(namedFont.name)
    }
}
```

You can make the above view represent a constant number of views by wrapping the condition in a [VStack](VStack.zh-Hans.md), an [HStack](HStack.zh-Hans.md), or a [ZStack](ZStack.zh-Hans.md).

```swift
ForEach(namedFonts) { namedFont in
    VStack {
        if namedFont.name.count != 2 {
            Text(namedFont.name)
        }
    }
}
```

When enabling the following launch argument, SwiftUI will log when it encounters a view that produces a non-constant number of views in these containers:

```swift
-LogForEachSlowPath YES
```

## Creating a collection

- **init(_:)**: Creates an instance that uniquely identifies and creates table rows across updates based on the identity of the underlying data.
- **init(_:content:)**: Creates an instance that uniquely identifies and creates map content across updates based on the identity of the underlying data.
- **init(_:id:content:)**: Creates an instance that uniquely identifies and creates map content across updates based on the provided key path to the underlying data’s identifier.

## Creating an editable collection

- **init(_:editActions:content:)**: Creates an instance that uniquely identifies and creates views across updates based on the identity of the underlying data.
- **init(_:id:editActions:content:)**: Creates an instance that uniquely identifies and creates views across updates based on the identity of the underlying data.

## Accessing content

- **content**: A function to create content on demand using the underlying data.
- **data**: The collection of underlying identified data that SwiftUI uses to create views dynamically.

## Initializers

- **init(sections:content:)**: Creates an instance that uniquely identifies and creates views across updates based on the sections of a given view.
- **init(subviews:content:)**: Creates an instance that uniquely identifies and creates views across updates based on the subviews of a given view.

## Iterating over dynamic data

- **ForEachSectionCollection**: A collection which allows a view to be treated as a collection of its sections in a for each loop.
- **ForEachSubviewCollection**: A collection which allows a view to be treated as a collection of its subviews in a for each loop.
- **DynamicViewContent**: A type of view that generates views from an underlying collection of data.

## Conforms To

- AccessibilityRotorContent
- AttachmentContent
- Chart3DContent
- ChartContent
- Copyable
- DynamicMapContent
- DynamicTableRowContent
- DynamicViewContent
- MapContent
- TabContent
- TableRowContent
- View

