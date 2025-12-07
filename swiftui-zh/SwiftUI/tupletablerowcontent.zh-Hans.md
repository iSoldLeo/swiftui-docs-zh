---
来源： https://developer.apple.com/documentation/swiftui/tupletablerowcontent
抓取时间： 2025-12-04T13:37:05Z
---

# TupleTableRowContent

**Structure**

一种表格列内容类型，用于创建由 Swift 表格行元组创建的表格行。

### 声明

```swift
@frozen struct TupleTableRowContent<Value, T> where Value : Identifiable
```

## 概览

不要直接使用此类型；相反，SwiftUI 将此类型用作 `buildBlock` 中各种 [TableRowBuilder](TableRowBuilder.zh-Hans.md) 方法的返回值。元组的大小与在`rows` 闭包中为[Table](Table.zh-Hans.md) 初始化器创建的列数相对应。

## 访问值

- **value**

## 创建行

- **TableRow**：表示表中数据值的行。
- **TableRowContent**：用于表示表格行的类型。
- **TableHeaderRowContent**：显示单一视图而非分栏内容的表格行。
- **TableForEachContent**：一种表行内容类型，通过对集合进行迭代来创建表行。
- **EmptyTableRowContent**：不产生任何行的表行内容。
- **DynamicTableRowContent**：一种从底层数据集合生成表行的表行内容。
- **TableRowBuilder**：从闭包创建表格行内容的结果生成器。

## 符合

- TableRowContent


---
source: https://developer.apple.com/documentation/swiftui/tupletablerowcontent
crawled: 2025-12-04T13:37:05Z
---

# TupleTableRowContent

**Structure**

A type of table column content that creates table rows created from a Swift tuple of table rows.

## Declaration

```swift
@frozen struct TupleTableRowContent<Value, T> where Value : Identifiable
```

## Overview

Don’t use this type directly; instead, SwiftUI uses this type as the return value from the various `buildBlock` methods in [TableRowBuilder](TableRowBuilder.zh-Hans.md). The size of the tuple corresponds to how many columns you create in the `rows` closure you provide to the [Table](Table.zh-Hans.md) initializer.

## Accessing the value

- **value**

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableRowContent**: A type used to represent table rows.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Conforms To

- TableRowContent

