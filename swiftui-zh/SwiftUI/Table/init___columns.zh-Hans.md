--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(_:columns:)

抓取时间：2025-12-01T00:42:55Z

---

# init(_:columns:)

**Initializer**

创建一个表格，该表格根据一组可识别的数据计算其行。

## 声明

```swift
nonisolated init<Data>(_ data: Data, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## 参数

- **data**：用于计算表格行的可识别数据。

- **columns**：要在表格中显示的列。

## 根据列创建表

- **init(_:selection:columns:)**：创建一个基于可识别数据集合计算行的表，并支持选择多行。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(_:columns:)
crawled: 2025-12-01T00:42:55Z
---

# init(_:columns:)

**Initializer**

Creates a table that computes its rows based on a collection of identifiable data.

## Declaration

```swift
nonisolated init<Data>(_ data: Data, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## Parameters

- **data**: The identifiable data for computing the table rows.
- **columns**: The columns to display in the table.

## Creating a table from columns

- **init(_:selection:columns:)**: Creates a table that computes its rows based on a collection of identifiable data, and that supports selecting multiple rows.

