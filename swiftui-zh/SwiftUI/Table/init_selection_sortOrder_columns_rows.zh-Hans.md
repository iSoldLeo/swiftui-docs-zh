--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(selection:sortOrder:columns:rows:)

抓取时间：2025-12-01T00:43:02Z

---

# init(selection:sortOrder:columns:rows:)

**Initializer**

创建一个可排序的表格，表格包含指定的列和行，并支持选择多行。

## 声明

```swift
nonisolated init<Sort>(selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## 参数

- **selection**：绑定到一个集合，该集合标识所选行的 ID。

- **sortOrder**：绑定到列的排序规则。

- **columns**：要在表格中显示的列。

- **rows**：表格中要显示的行。

## 根据列和行创建可排序表格

- **init(of:sortOrder:columns:rows:)**：使用指定的列和行创建可排序表格。

- **init(of:selection:sortOrder:columns:rows:)**：使用指定的列和行创建支持多行选择的可排序表格。

- **init(sortOrder:columns:rows:)**：使用指定的列和行创建可排序表格。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(selection:sortOrder:columns:rows:)
crawled: 2025-12-01T00:43:02Z
---

# init(selection:sortOrder:columns:rows:)

**Initializer**

Creates a sortable table with the given columns and rows that supports selecting multiple rows.

## Declaration

```swift
nonisolated init<Sort>(selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## Parameters

- **selection**: A binding to a set that identifies selected rows ids.
- **sortOrder**: A binding to the ordered sorting of columns.
- **columns**: The columns to display in the table.
- **rows**: The rows to display in the table.

## Creating a sortable table from columns and rows

- **init(of:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows.
- **init(of:selection:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows.
- **init(sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows.

