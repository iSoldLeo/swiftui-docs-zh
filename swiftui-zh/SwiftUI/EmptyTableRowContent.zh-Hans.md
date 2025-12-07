--- 来源：https://developer.apple.com/documentation/SwiftUI/EmptyTableRowContent
抓取时间：2025-12-02T17:40:03Z

---

# EmptyTableRowContent

**Structure**

不生成任何行的表格行内容。

## 声明

```swift
struct EmptyTableRowContent<Value> where Value : Identifiable
```

## 概述

您几乎不需要直接创建 `EmptyTableRowContent`。相反，`EmptyTableRowContent` 表示缺少行。

## 创建行

- **TableRow**：表示表格中数据值的行。

- **TableRowContent**：用于表示表格行的类型。

- **TableHeaderRowContent**：显示单列视图而非列式内容的表格行。

- **TupleTableRowContent**：一种表格列内容类型，它根据 Swift 表格行元组创建表格行。

- **TableForEachContent**：一种表格行内容类型，它通过遍历集合创建表格行。

- **DynamicTableRowContent**：一种表格行内容类型，它根据底层数据集合生成表格行。

- **TableRowBuilder**：一种结果构建器，它根据闭包创建表格行内容。

## 符合以下规范

- Copyable

- TableRowContent


---
source: https://developer.apple.com/documentation/SwiftUI/EmptyTableRowContent
crawled: 2025-12-02T17:40:03Z
---

# EmptyTableRowContent

**Structure**

A table row content that doesn’t produce any rows.

## Declaration

```swift
struct EmptyTableRowContent<Value> where Value : Identifiable
```

## Overview

You will rarely, if ever, need to create an `EmptyTableRowContent` directly. Instead, `EmptyTableRowContent` represents the absence of a row.

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableRowContent**: A type used to represent table rows.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Conforms To

- Copyable
- TableRowContent

