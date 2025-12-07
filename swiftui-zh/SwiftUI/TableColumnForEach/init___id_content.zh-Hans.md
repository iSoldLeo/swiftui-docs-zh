--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnForEach/init(_:id:content:)

抓取时间：2025-12-03T06:41:02Z

---

# init(_:id:content:)

**Initializer**

创建一个实例，该实例基于提供的指向底层数据标识符的键路径，在更新过程中唯一标识并创建表列。

## 声明

```swift
init(_ data: Data, id: KeyPath<Data.Element, ID>, @TableColumnBuilder<TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableRowValue, TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableColumnSortComparator> content: @escaping (Data.Element) -> Content)
```

## 参数

- **data**：[TableColumnForEach](../TableColumnForEach.zh-Hans.md) 实例用于动态创建表列的数据。

- **id**：指向所提供数据标识符的键路径。

- **content**：表格列构建器，可为每个元素动态创建列。

## 创建集合

- **init(_:content:)**：创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建表格列。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnForEach/init(_:id:content:)
crawled: 2025-12-03T06:41:02Z
---

# init(_:id:content:)

**Initializer**

Creates an instance that uniquely identifies and creates table columns across updates based on the provided key path to the underlying data’s identifier.

## Declaration

```swift
init(_ data: Data, id: KeyPath<Data.Element, ID>, @TableColumnBuilder<TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableRowValue, TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableColumnSortComparator> content: @escaping (Data.Element) -> Content)
```

## Parameters

- **data**: The data that the [TableColumnForEach](../TableColumnForEach.zh-Hans.md) instance uses to create table columns dynamically.
- **id**: The key path to the provided data’s identifier.
- **content**: The table column builder that creates columns dynamically for each element.

## Creating the collection

- **init(_:content:)**: Creates an instance that uniquely identifies and creates table columns across updates based on the identity of the underlying data.

