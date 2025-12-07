---
来源： https://developer.apple.com/documentation/SwiftUI/TupleTableColumnContent
抓取时间： 2025-12-03T06:40:32Z
---

# TupleTableColumnContent

**Structure**

一种表列内容类型，用于创建由 Swift 表列元组创建的表列。

### 声明

```swift
@frozen struct TupleTableColumnContent<RowValue, Sort, T> where RowValue : Identifiable, Sort : SortComparator
```

## 概览

不要直接使用此类型；相反，SwiftUI 将此类型用作 `buildBlock` 中各种 [TableColumnBuilder](TableColumnBuilder.zh-Hans.md) 方法的返回值。元组的大小与在`columns` 闭包中为[Table](Table.zh-Hans.md) 初始化器创建的列数相对应。

## 访问值

- **value**：该列内容所显示行的值。

## 符合

- TableColumnContent


---
source: https://developer.apple.com/documentation/SwiftUI/TupleTableColumnContent
crawled: 2025-12-03T06:40:32Z
---

# TupleTableColumnContent

**Structure**

A type of table column content that creates table columns created from a Swift tuple of table columns.

## Declaration

```swift
@frozen struct TupleTableColumnContent<RowValue, Sort, T> where RowValue : Identifiable, Sort : SortComparator
```

## Overview

Don’t use this type directly; instead, SwiftUI uses this type as the return value from the various `buildBlock` methods in [TableColumnBuilder](TableColumnBuilder.zh-Hans.md). The size of the tuple corresponds to how many columns you create in the `columns` closure you provide to the [Table](Table.zh-Hans.md) initializer.

## Accessing the value

- **value**: The value of a row presented by this column content.

## Conforms To

- TableColumnContent

