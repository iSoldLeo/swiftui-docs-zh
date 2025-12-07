--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnForEach/init(_:content:)

抓取时间：2025-12-01T11:30:18Z

---

# init(_:content:)

**Initializer**

创建一个实例，该实例基于底层数据的标识，在更新过程中唯一标识并创建表列。

## 声明

```swift
init(_ data: Data, @TableColumnBuilder<TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableRowValue, TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableColumnSortComparator> content: @escaping (Data.Element) -> Content) where ID == Data.Element.ID, Data.Element : Identifiable
```

## 参数

- **data**：[TableColumnForEach](../TableColumnForEach.zh-Hans.md) 实例用于动态创建表列的标识数据。

- **content**：为每个元素动态创建表列的表列构建器。

## 创建集合

- **init(_:id:content:)**：创建一个实例，该实例基于提供的指向底层数据标识符的键路径，在更新过程中唯一标识并创建表列。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnForEach/init(_:content:)
crawled: 2025-12-01T11:30:18Z
---

# init(_:content:)

**Initializer**

Creates an instance that uniquely identifies and creates table columns across updates based on the identity of the underlying data.

## Declaration

```swift
init(_ data: Data, @TableColumnBuilder<TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableRowValue, TableColumnForEach<Data, ID, RowValue, Sort, Content>.TableColumnSortComparator> content: @escaping (Data.Element) -> Content) where ID == Data.Element.ID, Data.Element : Identifiable
```

## Parameters

- **data**: The identified data that the [TableColumnForEach](../TableColumnForEach.zh-Hans.md) instance uses to create table columns dynamically.
- **content**: The table column builder that creates columns dynamically for each element.

## Creating the collection

- **init(_:id:content:)**: Creates an instance that uniquely identifies and creates table columns across updates based on the provided key path to the underlying data’s identifier.

