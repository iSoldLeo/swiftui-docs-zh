--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumn

抓取时间：2025-12-02T17:39:53Z

---

# TableColumn

**Structure**

用于显示表格中每一行视图的列。

## 声明

```swift
struct TableColumn<RowValue, Sort, Content, Label> where RowValue : Identifiable, Sort : SortComparator, Content : View, Label : View
```

## 概述

您可以创建一个包含标签、内容视图和可选键路径的列。表格会调用内容视图构建器，并将表格中每一行的值传递给它。该列使用键路径映射到每一行值的属性，可排序表格会使用该属性来反映当前的排序顺序。

以下示例为包含 `Person` 行的表创建一个可排序列，显示每个人的名字：

```swift
TableColumn("Given name", value: \.givenName) { person in
    Text(person.givenName)
}
```

对于常见的 `String` 属性，您可以使用便捷的初始化器，它不需要显式的内容闭包，而是将该字符串原样显示为 [Text](Text.zh-Hans.md) 视图。这意味着您可以将前面的示例写成：

```swift
TableColumn("Given name", value: \.givenName)
```

## 创建不可排序列

- **init(_:value:)**：创建一个不可排序的列，该列显示一个带有文本标签的字符串属性。

- **init(_:content:)**：创建一个不可排序的列，并带有文本标签

## 创建可排序的列

- **init(_:value:content:)**：创建一个可排序的列，用于显示布尔值，并带有文本标签。

- **init(_:value:comparator:)**：创建一个可排序的列，用于显示字符串属性，并带有文本标签。

- **init(_:value:comparator:content:)**：创建一个可排序的列，并带有文本标签。

- **init(_:sortUsing:content:)**：创建一个可排序的列，并带有文本标签。

## 设置列宽

- **width(_:)**：创建一个固定宽度的表格列，用户无法调整其大小。

- **width(min:ideal:max:)**：创建一个可调整大小的表格列，并设置相应的约束条件。

- **width()**：设置列宽。

## 创建列

- **TableColumnContent**：用于表示表中列的类型。

- **TableColumnAlignment**：描述表列内容的对齐方式。

- **TableColumnBuilder**：一个结果构建器，用于从闭包创建表列内容。

- **TableColumnForEach**：一个结构，用于根据底层已识别数据集合按需计算列。

## 符合以下规范

- TableColumnContent


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumn
crawled: 2025-12-02T17:39:53Z
---

# TableColumn

**Structure**

A column that displays a view for each row in a table.

## Declaration

```swift
struct TableColumn<RowValue, Sort, Content, Label> where RowValue : Identifiable, Sort : SortComparator, Content : View, Label : View
```

## Overview

You create a column with a label, content view, and optional key path. The table calls the content view builder with the value for each row in the table. The column uses a key path to map to a property of each row value, which sortable tables use to reflect the current sort order.

The following example creates a sortable column for a table with `Person` rows, displaying each person’s given name:

```swift
TableColumn("Given name", value: \.givenName) { person in
    Text(person.givenName)
}
```

For the common case of `String` properties, you can use the convenience initializer that doesn’t require an explicit content closure and displays that string verbatim as a [Text](Text.zh-Hans.md) view. This means you can write the previous example as:

```swift
TableColumn("Given name", value: \.givenName)
```

## Creating an unsortable column

- **init(_:value:)**: Creates an unsortable column that displays a string property with a text label.
- **init(_:content:)**: Creates an unsortable column with a text label

## Creating a sortable column

- **init(_:value:content:)**: Creates a sortable column for Boolean values with a text label.
- **init(_:value:comparator:)**: Creates a sortable column that displays a string property and has a text label.
- **init(_:value:comparator:content:)**: Creates a sortable column with a text label.
- **init(_:sortUsing:content:)**: Creates a sortable column with text label.

## Setting the column width

- **width(_:)**: Creates a fixed width table column that isn’t user resizable.
- **width(min:ideal:max:)**: Creates a resizable table column with the provided constraints.
- **width()**: Sets the column’s width.

## Creating columns

- **TableColumnContent**: A type used to represent columns within a table.
- **TableColumnAlignment**: Describes the alignment of the content of a table column.
- **TableColumnBuilder**: A result builder that creates table column content from closures.
- **TableColumnForEach**: A structure that computes columns on demand from an underlying collection of identified data.

## Conforms To

- TableColumnContent

