--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(_:selection:columns:)

抓取时间：2025-12-01T00:42:56Z

---

# init(_:selection:columns:)

**Initializer**

创建一个表格，该表格基于一组可识别的数据计算行，并支持选择多行。

## 声明

```swift
nonisolated init<Data>(_ data: Data, selection: Binding<Set<Value.ID>>, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## 参数

- **data**：用于计算表格行的可识别数据。

- **selection**：绑定到一个集合，该集合标识所选行的 ID。

- **columns**：要在表格中显示的列。

## 根据列创建表

- **init(_:columns:)**：创建一个表，该表根据一组可识别的数据计算其行。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(_:selection:columns:)
crawled: 2025-12-01T00:42:56Z
---

# init(_:selection:columns:)

**Initializer**

Creates a table that computes its rows based on a collection of identifiable data, and that supports selecting multiple rows.

## Declaration

```swift
nonisolated init<Data>(_ data: Data, selection: Binding<Set<Value.ID>>, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## Parameters

- **data**: The identifiable data for computing the table rows.
- **selection**: A binding to a set that identifies selected rows IDs.
- **columns**: The columns to display in the table.

## Creating a table from columns

- **init(_:columns:)**: Creates a table that computes its rows based on a collection of identifiable data.

