---
来源： https://developer.apple.com/documentation/SwiftUI/TableRowBuilder
抓取时间： 2025-12-02T17:40:05Z
---

# TableRowBuilder

**Structure**

从闭包创建表格行内容的结果生成器。

### 声明

```swift
@resultBuilder struct TableRowBuilder<Value> where Value : Identifiable
```

## 概览

该类型中的`buildBlock` 方法根据作为参数提供的源的数量和类型创建[TableRowContent](TableRowContent.zh-Hans.md) 实例。

请不要直接使用此类型；相反，SwiftUI 会为各种 [Table](Table.zh-Hans.md) 初始化器的`rows` 参数注释`@TableRowBuilder` 注释，隐式地为您调用此构建器。

## 从源代码创建一行

- **buildBlock(_:)**：创建单行结果。
- **buildBlock(_:_:)**：从两个来源创建一行结果。
- **buildBlock(_:_:_:)**：从三个来源创建行结果。
- **buildBlock(_:_:_:_:)**：从四个来源创建行结果。
- **buildBlock(_:_:_:_:_:)**：从五个数据源创建行结果。
- **buildBlock(_:_:_:_:_:_:)**：从六个数据源创建行结果。
- **buildBlock(_:_:_:_:_:_:_:)**：从七个数据源创建行结果。
- **buildBlock(_:_:_:_:_:_:_:_:)**：从八个来源创建行结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:)**：从九个数据源创建行结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**：从 10 个数据源创建行结果。

## 从条件中创建行

- **buildIf(_:)**：为条件语句创建行结果。
- **buildEither(first:)**：为两个行内容备选方案中的第一个创建行结果。
- **buildEither(second:)**：为两个行内容备选方案中的第二个创建行结果。
- **buildExpression(_:)**：在构建器中构建表达式。

## 创建行

- **TableRow**：表示表格中数据值的行。
- **TableRowContent**：用于表示表格行的类型。
- **TableHeaderRowContent**：显示单一视图而非分栏内容的表格行。
- **TupleTableRowContent**：一种表格列内容类型，可创建由 Swift 表格行元组创建的表格行。
- **TableForEachContent**：表行内容类型，用于创建通过遍历集合创建的表行。
- **EmptyTableRowContent**：不产生任何行的表行内容。
- **DynamicTableRowContent**：一种表行内容，可从底层数据集合生成表行。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowBuilder
crawled: 2025-12-02T17:40:05Z
---

# TableRowBuilder

**Structure**

A result builder that creates table row content from closures.

## Declaration

```swift
@resultBuilder struct TableRowBuilder<Value> where Value : Identifiable
```

## Overview

The `buildBlock` methods in this type create [TableRowContent](TableRowContent.zh-Hans.md) instances based on the number and types of sources provided as parameters.

Don’t use this type directly; instead, SwiftUI annotates the `rows` parameter of the various [Table](Table.zh-Hans.md) initializers with the `@TableRowBuilder` annotation, implicitly calling this builder for you.

## Building a row from sources

- **buildBlock(_:)**: Creates a single row result.
- **buildBlock(_:_:)**: Creates a row result from two sources.
- **buildBlock(_:_:_:)**: Creates a row result from three sources.
- **buildBlock(_:_:_:_:)**: Creates a row result from four sources.
- **buildBlock(_:_:_:_:_:)**: Creates a row result from five sources.
- **buildBlock(_:_:_:_:_:_:)**: Creates a row result from six sources.
- **buildBlock(_:_:_:_:_:_:_:)**: Creates a row result from seven sources.
- **buildBlock(_:_:_:_:_:_:_:_:)**: Creates a row result from eight sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:)**: Creates a row result from nine sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**: Creates a row result from ten sources.

## Building a row from conditionals

- **buildIf(_:)**: Creates a row result for conditional statements.
- **buildEither(first:)**: Creates a row result for the first of two row content alternatives.
- **buildEither(second:)**: Creates a row result for the second of two row content alternatives.
- **buildExpression(_:)**: Builds an expression within the builder.

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableRowContent**: A type used to represent table rows.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.

