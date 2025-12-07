--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(_:sortOrder:columns:)

抓取时间：2025-12-01T00:42:57Z

---

# init(_:sortOrder:columns:)

**Initializer**

创建一个可排序的表格，该表格根据一组可识别的数据计算其行。

## 声明

```swift
nonisolated init<Data, Sort>(_ data: Data, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Sort : SortComparator, Columns.TableRowValue == Data.Element, Data.Element == Sort.Compared
```

## 参数

- **data**：用于计算表格行的可识别数据。

- **sortOrder**：列排序的绑定。

- **columns**：要在表格中显示的列。

## 根据列创建可排序表格

- **init(_:selection:sortOrder:columns:)**：创建一个可排序的表格，该表格根据一组可识别的数据计算行，并支持选择多行。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(_:sortOrder:columns:)
crawled: 2025-12-01T00:42:57Z
---

# init(_:sortOrder:columns:)

**Initializer**

Creates a sortable table that computes its rows based on a collection of identifiable data.

## Declaration

```swift
nonisolated init<Data, Sort>(_ data: Data, sortOrder: Binding<[Sort]>, @TableColumnBuilder<Value, Sort> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Sort : SortComparator, Columns.TableRowValue == Data.Element, Data.Element == Sort.Compared
```

## Parameters

- **data**: The identifiable data for computing the table rows.
- **sortOrder**: A binding to the ordered sorting of columns.
- **columns**: The columns to display in the table.

## Creating a sortable table from columns

- **init(_:selection:sortOrder:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data, and supports selecting multiple rows.

