---
来源： https://developer.apple.com/documentation/SwiftUI/TableHeaderRowContent
抓取时间：2025-12-02T17:40:00Z
---

# 表格标题行内容

**Structure**

显示单一视图而非分栏内容的表格行。

## 声明

```swift
struct TableHeaderRowContent<Value, Content> where Value : Identifiable, Content : View
```

## 概览

您不能直接创建此类型。而是由框架代为创建。

## 创建行

- 行：表示表中数据值的行。
- **TableRowContent**：用于表示表格行的类型。
- **TupleTableRowContent**：一种表列内容类型，用于创建由表行的 Swift 元组创建的表行。
- **TableForEachContent**：表行内容类型，用于创建通过遍历集合创建的表行。
- **EmptyTableRowContent**：不产生任何行的表行内容。
- **DynamicTableRowContent**：一种从底层数据集合生成表行的表行内容。
- **TableRowBuilder**：从闭包创建表格行内容的结果生成器。

## 符合

- TableRowContent


---
source: https://developer.apple.com/documentation/SwiftUI/TableHeaderRowContent
crawled: 2025-12-02T17:40:00Z
---

# TableHeaderRowContent

**Structure**

A table row that displays a single view instead of columned content.

## Declaration

```swift
struct TableHeaderRowContent<Value, Content> where Value : Identifiable, Content : View
```

## Overview

You do not create this type directly. The framework creates it on your behalf.

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableRowContent**: A type used to represent table rows.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Conforms To

- TableRowContent

