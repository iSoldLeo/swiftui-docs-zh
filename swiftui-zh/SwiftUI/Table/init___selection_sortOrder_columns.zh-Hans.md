--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(_:selection:sortOrder:columns:)

抓取时间：2025-12-01T00:42:58Z

---

# init(_:selection:sortOrder:columns:)

**Initializer**

创建一个可排序的表格，该表格基于一组可识别的数据计算其行，并支持选择多行。

## 声明

```swift
nonisolated init<Data, Sort>(_ data: Data, selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Sort : SortComparator, Columns.TableRowValue == Data.Element, Data.Element == Sort.Compared
```

## 参数

- **data**：用于计算表格行的可识别数据。

- **selection**：绑定到一个集合，该集合标识所选行的 ID。

- **sortOrder**：绑定到列的有序排序。

- **columns**：表格中要显示的列。

## 根据列创建可排序表格

- **init(_:sortOrder:columns:)**：创建一个可排序表格，该表格根据一组可识别的数据计算其行。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(_:selection:sortOrder:columns:)
crawled: 2025-12-01T00:42:58Z
---

# init(_:selection:sortOrder:columns:)

**Initializer**

Creates a sortable table that computes its rows based on a collection of identifiable data, and supports selecting multiple rows.

## Declaration

```swift
nonisolated init<Data, Sort>(_ data: Data, selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Sort : SortComparator, Columns.TableRowValue == Data.Element, Data.Element == Sort.Compared
```

## Parameters

- **data**: The identifiable data for computing the table rows.
- **selection**: A binding to a set that identifies selected rows IDs.
- **sortOrder**: A binding to the ordered sorting of columns.
- **columns**: The columns to display in the table.

## Creating a sortable table from columns

- **init(_:sortOrder:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data.

