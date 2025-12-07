--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment
抓取时间：2025-12-02T17:39:54Z

---

# TableColumnAlignment

**Structure**

描述表格列内容的对齐方式。

## 声明

```swift
struct TableColumnAlignment
```

## 概述

列的对齐方式既适用于其标题标签，也适用于每行内容视图的默认对齐方式。

## 获取对齐方式

- **automatic**：默认列对齐方式。

- **leading**：前导列对齐方式。

- **center**：居中列对齐方式。

- **trailing**：尾随列对齐方式。

- **numeric**：适用于数值内容的列对齐方式。

- **numeric(_:)**：适用于数值内容的列对齐方式。

## 创建列

- **TableColumn**：用于显示表中每一行视图的列。

- **TableColumnContent**：用于表示表中列的类型。

- **TableColumnBuilder**：用于从闭包创建表列内容的生成结果。

- **TableColumnForEach**：用于根据底层已识别数据集合按需计算列的结构。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment
crawled: 2025-12-02T17:39:54Z
---

# TableColumnAlignment

**Structure**

Describes the alignment of the content of a table column.

## Declaration

```swift
struct TableColumnAlignment
```

## Overview

The alignment of a column applies to both its header label as well as the default alignment of its content view for each row.

## Getting the alignment

- **automatic**: The default column alignment.
- **leading**: Leading column alignment.
- **center**: Center column alignment.
- **trailing**: Trailing column alignment.
- **numeric**: Column alignment appropriate for numeric content.
- **numeric(_:)**: Column alignment appropriate for numeric content.

## Creating columns

- **TableColumn**: A column that displays a view for each row in a table.
- **TableColumnContent**: A type used to represent columns within a table.
- **TableColumnBuilder**: A result builder that creates table column content from closures.
- **TableColumnForEach**: A structure that computes columns on demand from an underlying collection of identified data.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

