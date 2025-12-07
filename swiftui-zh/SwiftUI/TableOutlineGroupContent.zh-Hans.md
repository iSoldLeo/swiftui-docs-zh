---
来源： https://developer.apple.com/documentation/SwiftUI/TableOutlineGroupContent
抓取时间： 2025-12-02T17:40:07Z
---

# TableOutlineGroupContent

**Structure**

由表的分层初始化程序创建的不透明表行类型。

### 声明

```swift
struct TableOutlineGroupContent<Data> where Data : RandomAccessCollection, Data.Element : Identifiable
```

## 概览

该行内容由`Table.init(_:,children:,...)` 初始化程序创建，作为表的`Rows` 通用类型。

要显式创建分层行，请使用 [OutlineGroup](OutlineGroup.zh-Hans.md) 代替。

## 添加渐进式披露

- **DisclosureTableRow**：一种根据披露控件的状态显示或隐藏附加行的表格行。

## 符合

- 表行内容


---
source: https://developer.apple.com/documentation/SwiftUI/TableOutlineGroupContent
crawled: 2025-12-02T17:40:07Z
---

# TableOutlineGroupContent

**Structure**

An opaque table row type created by a table’s hierarchical initializers.

## Declaration

```swift
struct TableOutlineGroupContent<Data> where Data : RandomAccessCollection, Data.Element : Identifiable
```

## Overview

This row content is created by `Table.init(_:,children:,...)` initializers as the table’s `Rows` generic type.

To explicitly create hierarchical rows, use [OutlineGroup](OutlineGroup.zh-Hans.md) instead.

## Adding progressive disclosure

- **DisclosureTableRow**: A kind of table row that shows or hides additional rows based on the state of a disclosure control.

## Conforms To

- TableRowContent

