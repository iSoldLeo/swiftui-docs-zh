---
来源： https://developer.apple.com/documentation/SwiftUI/TableForEachContent
抓取时间： 2025-12-02T17:40:02Z
---

# TableForEachContent

**Structure**

一种表格行内容类型，通过遍历集合创建表格行。

### 声明

```swift
struct TableForEachContent<Data> where Data : RandomAccessCollection, Data.Element : Identifiable
```

## 概览

您不会直接使用此类型。各种 `Table.init(_:,...)` 初始化程序将此类型创建为表的`Rows` 通用类型。

要显式创建基于动态集合的行，请使用 [ForEach](ForEach.zh-Hans.md) 代替。

## 创建行

- **TableRow**：表示表中数据值的行。
- **TableRowContent**：用于表示表格行的类型。
- **TableHeaderRowContent**：显示单一视图而非分栏内容的表格行。
- **TupleTableRowContent**：一种表格列内容类型，可创建由 Swift 表格行元组创建的表格行。
- **EmptyTableRowContent**：不产生任何行的表行内容。
- **DynamicTableRowContent**：一种从底层数据集合生成表行的表行内容。
- **TableRowBuilder**：从闭包创建表格行内容的结果生成器。

## 符合

- TableRowContent


---
source: https://developer.apple.com/documentation/SwiftUI/TableForEachContent
crawled: 2025-12-02T17:40:02Z
---

# TableForEachContent

**Structure**

A type of table row content that creates table rows created by iterating over a collection.

## Declaration

```swift
struct TableForEachContent<Data> where Data : RandomAccessCollection, Data.Element : Identifiable
```

## Overview

You don’t use this type directly. The various `Table.init(_:,...)` initializers create this type as the table’s `Rows` generic type.

To explicitly create dynamic collection-based rows, use [ForEach](ForEach.zh-Hans.md) instead.

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableRowContent**: A type used to represent table rows.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Conforms To

- TableRowContent

