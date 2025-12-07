---
来源： https://developer.apple.com/documentation/swiftui/tablecolumnbuilder
抓取时间： 2025-12-04T13:36:49Z
---

# 表列生成器

**Structure**

从闭包创建表格列内容的结果生成器。

### 声明

```swift
@resultBuilder struct TableColumnBuilder<RowValue, Sort> where RowValue : Identifiable, Sort : SortComparator
```

## 概览

该类型中的`buildBlock` 方法根据作为参数提供的源的数量和类型创建[TableColumnContent](TableColumnContent.zh-Hans.md) 实例。

请不要直接使用此类型；相反，SwiftUI 会为各种 [Table](Table.zh-Hans.md) 初始化器的`columns` 参数注释`@TableColumnBuilder` 注释，隐式地为您调用此构建器。

## 创建列

- **buildBlock(_:)**：创建一个单一的、不可排序的列结果。
- **buildBlock(_:_:)**：从两个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:)**：从三个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:)**：从四个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:)**：从五个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:)**：从六个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:)**：从七个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:)**：从八个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:)**：从九个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**：从 10 个来源创建一个无法排序的列结果。
- **buildExpression(_:)**：创建通用的、不可排序的单列表达式。

## 支持类型

- **TupleTableColumnContent**：表列内容类型，用于创建由 Swift 表列元组创建的表列。

### 类型方法

- **buildEither(first:)**：为两个列内容选项中的第一个创建列结果。
- **buildEither(second:)**：为两个行内容备选方案中的第二个创建行结果。
- **buildIf(_:)**：为两个行内容备选方案的第二个创建行结果。
- **buildLimitedAvailability(_:)**

## 创建列

- **TableColumn**：为表格中的每一行显示视图的列。
- **TableColumnContent**：用于表示表格中列的类型。
- **TableColumnAlignment**：描述表格列内容的对齐方式。
- **TableColumnForEach**：一种结构，可根据需要从底层识别数据集合中计算列。


---
source: https://developer.apple.com/documentation/swiftui/tablecolumnbuilder
crawled: 2025-12-04T13:36:49Z
---

# TableColumnBuilder

**Structure**

A result builder that creates table column content from closures.

## Declaration

```swift
@resultBuilder struct TableColumnBuilder<RowValue, Sort> where RowValue : Identifiable, Sort : SortComparator
```

## Overview

The `buildBlock` methods in this type create [TableColumnContent](TableColumnContent.zh-Hans.md) instances based on the number and types of sources provided as parameters.

Don’t use this type directly; instead, SwiftUI annotates the `columns` parameter of the various [Table](Table.zh-Hans.md) initializers with the `@TableColumnBuilder` annotation, implicitly calling this builder for you.

## Building a column

- **buildBlock(_:)**: Creates a single, unsortable column result.
- **buildBlock(_:_:)**: Creates an unsortable column result from two sources.
- **buildBlock(_:_:_:)**: Creates an unsortable column result from three sources.
- **buildBlock(_:_:_:_:)**: Creates an unsortable column result from four sources.
- **buildBlock(_:_:_:_:_:)**: Creates an unsortable column result from five sources.
- **buildBlock(_:_:_:_:_:_:)**: Creates an unsortable column result from six sources.
- **buildBlock(_:_:_:_:_:_:_:)**: Creates an unsortable column result from seven sources.
- **buildBlock(_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from eight sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from nine sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from ten sources.
- **buildExpression(_:)**: Creates a generic, unsortable single column expression.

## Supporting types

- **TupleTableColumnContent**: A type of table column content that creates table columns created from a Swift tuple of table columns.

## Type Methods

- **buildEither(first:)**: Creates a column result for the first of two column content alternatives.
- **buildEither(second:)**: Creates a row result for the second of two row content alternatives.
- **buildIf(_:)**
- **buildLimitedAvailability(_:)**

## Creating columns

- **TableColumn**: A column that displays a view for each row in a table.
- **TableColumnContent**: A type used to represent columns within a table.
- **TableColumnAlignment**: Describes the alignment of the content of a table column.
- **TableColumnForEach**: A structure that computes columns on demand from an underlying collection of identified data.

