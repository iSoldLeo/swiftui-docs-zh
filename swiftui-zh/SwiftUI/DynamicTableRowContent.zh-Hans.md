---
来源： https://developer.apple.com/documentation/SwiftUI/DynamicTableRowContent
抓取时间： 2025-12-02T17:40:04Z
---

# DynamicTableRowContent

**Protocol**

一种表格行内容类型，可从底层数据集合生成表格行。

### 声明

```swift
protocol DynamicTableRowContent : TableRowContent
```

## 概览

这种表格行内容类型为表格提供拖放支持。使用[onInsert(of:perform:)](DynamicTableRowContent/onInsert_of_perform.zh-Hans.md)修饰符添加一个操作，以便在表格向其底层集合插入新内容时调用。

## 获取行数据

- **data**：底层数据集合。
- **Data**：基础数据集合的类型。

## 插入行

- **onInsert(of:perform:)**：设置动态表行的插入操作。
- **OnInsertTableRowModifier**：表行修改器，可在某些基本行内容中添加插入数据的功能。

## 支持拖放

- **dropDestination(for:action:)**：设置动态表行的插入操作。

## 创建行

- **TableRow**：表示表中数据值的行。
- **TableRowContent**：用于表示表格行的类型。
- **TableHeaderRowContent**：显示单一视图而非分栏内容的表格行。
- **TupleTableRowContent**：一种表格列内容类型，可创建由 Swift 表格行元组创建的表格行。
- **TableForEachContent**：表行内容类型，用于创建通过遍历集合创建的表行。
- **EmptyTableRowContent**：不产生任何行的表行内容。
- **TableRowBuilder**：从闭包创建表行内容的结果生成器。

## 继承自

- 表行内容

## 符合类型

- 换行
- 修改内容


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicTableRowContent
crawled: 2025-12-02T17:40:04Z
---

# DynamicTableRowContent

**Protocol**

A type of table row content that generates table rows from an underlying collection of data.

## Declaration

```swift
protocol DynamicTableRowContent : TableRowContent
```

## Overview

This table row content type provides drag-and-drop support for tables. Use the [onInsert(of:perform:)](DynamicTableRowContent/onInsert_of_perform.zh-Hans.md) modifier to add an action to call when the table inserts new contents into its underlying collection.

## Getting row data

- **data**: The collection of underlying data.
- **Data**: The type of the underlying collection of data.

## Inserting rows

- **onInsert(of:perform:)**: Sets the insert action for the dynamic table rows.
- **OnInsertTableRowModifier**: A table row modifier that adds the ability to insert data in some base row content.

## Supporting drag and drop

- **dropDestination(for:action:)**: Sets the insert action for the dynamic table rows.

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableRowContent**: A type used to represent table rows.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Inherits From

- TableRowContent

## Conforming Types

- ForEach
- ModifiedContent

