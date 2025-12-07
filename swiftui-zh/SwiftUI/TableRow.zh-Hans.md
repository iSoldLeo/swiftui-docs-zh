---
来源： https://developer.apple.com/documentation/SwiftUI/TableRow
抓取时间： 2025-12-02T17:39:59Z
---

# TableRow

**Structure**

表示表格中数据值的行。

## 声明

```swift
struct TableRow<Value> where Value : Identifiable
```

## 概览

在[Table](Table.zh-Hans.md) 初始化器中为`rows` 参数提供的闭包中创建[TableRow](TableRow.zh-Hans.md) 实例，这些闭包包含列和行。表格将行的值提供给表格的每一列，从而产生列中每一行的单元格。

## 创建一行

- **init(_:)**：为给定值创建表格行。

## 创建行

- **TableRowContent**：用于表示表格行的类型。
- **TableHeaderRowContent**：显示单一视图而非分栏内容的表格行。
- **TupleTableRowContent**：一种表格列内容类型，可创建由 Swift 表格行元组创建的表格行。
- **TableForEachContent**：表行内容类型，用于创建通过遍历集合创建的表行。
- **EmptyTableRowContent**：不产生任何行的表行内容。
- **DynamicTableRowContent**：一种从底层数据集合生成表行的表行内容。
- **TableRowBuilder**：从闭包创建表格行内容的结果生成器。

## 符合

- TableRowContent


---
source: https://developer.apple.com/documentation/SwiftUI/TableRow
crawled: 2025-12-02T17:39:59Z
---

# TableRow

**Structure**

A row that represents a data value in a table.

## Declaration

```swift
struct TableRow<Value> where Value : Identifiable
```

## Overview

Create instances of [TableRow](TableRow.zh-Hans.md) in the closure you provide to the `rows` parameter in [Table](Table.zh-Hans.md) initializers that take columns and rows. The table provides the value of a row to each column of a table, which produces the cells for each row in the column.

## Creating a row

- **init(_:)**: Creates a table row for the given value.

## Creating rows

- **TableRowContent**: A type used to represent table rows.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Conforms To

- TableRowContent

