--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(of:sortOrder:columns:rows:)

抓取时间：2025-12-01T00:43:00Z

---

# init(of:sortOrder:columns:rows:)

**Initializer**

创建一个具有指定列和行的可排序表格。

## 声明

```swift
nonisolated init<Sort>(of valueType: Value.Type, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## 参数

- **valueType**：用于获取表格内容的值类型。

- **sortOrder**：列排序的绑定。

- **columns**：要在表格中显示的列。

- **rows**：表格中要显示的行。

## 根据列和行创建可排序表格

- **init(of:selection:sortOrder:columns:rows:)**：使用指定的列和行创建可排序表格，并支持多行选择。

- **init(sortOrder:columns:rows:)**：使用指定的列和行创建可排序表格。

- **init(selection:sortOrder:columns:rows:)**：使用指定的列和行创建可排序表格，并支持多行选择。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(of:sortOrder:columns:rows:)
crawled: 2025-12-01T00:43:00Z
---

# init(of:sortOrder:columns:rows:)

**Initializer**

Creates a sortable table with the given columns and rows.

## Declaration

```swift
nonisolated init<Sort>(of valueType: Value.Type, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## Parameters

- **valueType**: The type of value used to derive the table’s contents.
- **sortOrder**: A binding to the ordered sorting of columns.
- **columns**: The columns to display in the table.
- **rows**: The rows to display in the table.

## Creating a sortable table from columns and rows

- **init(of:selection:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows.
- **init(sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows.
- **init(selection:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows.

