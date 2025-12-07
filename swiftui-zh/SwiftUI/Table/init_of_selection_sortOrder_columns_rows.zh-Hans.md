--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(of:selection:sortOrder:columns:rows:)

抓取时间：2025-12-02T20:58:57Z

---

# init(of:selection:sortOrder:columns:rows:)

**Initializer**

创建一个具有指定列和行的可排序表格，支持选择多行。

## 声明

```swift
nonisolated init<Sort>(of valueType: Value.Type, selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## 参数

- **valueType**：用于获取表格内容的值类型。

- **selection**：绑定到用于标识所选行 ID 的集合。

- **sortOrder**：绑定到列的排序方式。

- **columns**：表格中要显示的列。

- **rows**：表格中要显示的行。

## 根据列和行创建可排序表格

- **init(of:sortOrder:columns:rows:)**：使用指定的列和行创建可排序表格。

- **init(sortOrder:columns:rows:)**：使用指定的列和行创建可排序表格。

- **init(selection:sortOrder:columns:rows:)**：使用指定的列和行创建支持多行选择的可排序表格。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(of:selection:sortOrder:columns:rows:)
crawled: 2025-12-02T20:58:57Z
---

# init(of:selection:sortOrder:columns:rows:)

**Initializer**

Creates a sortable table with the given columns and rows that supports selecting multiple rows.

## Declaration

```swift
nonisolated init<Sort>(of valueType: Value.Type, selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## Parameters

- **valueType**: The type of value used to derive the table’s contents.
- **selection**: A binding to a set that identifies selected rows ids.
- **sortOrder**: A binding to the ordered sorting of columns.
- **columns**: The columns to display in the table.
- **rows**: The rows to display in the table.

## Creating a sortable table from columns and rows

- **init(of:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows.
- **init(sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows.
- **init(selection:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows.

