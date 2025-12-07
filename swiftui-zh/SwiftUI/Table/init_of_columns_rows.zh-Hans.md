--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(of:columns:rows:)

抓取时间：2025-12-02T20:58:55Z

---

# init(of:columns:rows:)

**Initializer**

创建一个具有指定列和行的表格，并使用指定类型的值生成其内容。

## 声明

```swift
nonisolated init(of valueType: Value.Type, @TableColumnBuilder<Value, Never> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows)
```

## 参数

- **valueType**：用于生成表格内容的值的类型。

- **columns**：要在表格中显示的列。

- **rows**：要在表格中显示的行。

## 根据列和行创建表格

- **init(of:selection:columns:rows:)**：创建一个具有给定列和行的表格，支持选择多行，并使用给定类型的值生成数据。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(of:columns:rows:)
crawled: 2025-12-02T20:58:55Z
---

# init(of:columns:rows:)

**Initializer**

Creates a table with the given columns and rows that generates its contents using values of the given type.

## Declaration

```swift
nonisolated init(of valueType: Value.Type, @TableColumnBuilder<Value, Never> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows)
```

## Parameters

- **valueType**: The type of value used to derive the table’s contents.
- **columns**: The columns to display in the table.
- **rows**: The rows to display in the table.

## Creating a table from columns and rows

- **init(of:selection:columns:rows:)**: Creates a table with the given columns and rows that supports selecting multiple rows that generates its data using values of the given type.

