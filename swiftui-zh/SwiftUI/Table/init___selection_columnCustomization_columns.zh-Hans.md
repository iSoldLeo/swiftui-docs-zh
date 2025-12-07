--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(_:selection:columnCustomization:columns:)

抓取时间：2025-12-02T20:59:00Z

---

# init(_:selection:columnCustomization:columns:)

**Initializer**

创建一个表格，该表格基于一组可识别的数据计算行，支持选择多行，并且列可动态自定义。

## 声明

```swift
nonisolated init<Data>(_ data: Data, selection: Binding<Set<Value.ID>>, columnCustomization: Binding<TableColumnCustomization<Value>>, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## 参数

- **data**：用于计算表格行的可识别数据。

- **selection**：绑定到一个集合，该集合标识所选行的 ID。

- **columnCustomization**：绑定到列的状态。

- **columns**：要在表格中显示的列。

## 讨论

表格中每个需要进行自定义的列都必须有一个标识符，使用 [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md) 指定。

## 创建具有可自定义列的表格

- **init(_:columnCustomization:columns:)**：创建一个基于可识别数据集合计算行数并具有动态可自定义列的表格。

- **init(_:selection:sortOrder:columnCustomization:columns:)**：创建一个可排序的表格，该表格基于可识别数据集合计算行数，支持选择多行，并具有动态可自定义列。

- **init(_:sortOrder:columnCustomization:columns:)**：创建一个可排序的表格，该表格基于可识别数据集合计算行数并具有动态可自定义列。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(_:selection:columnCustomization:columns:)
crawled: 2025-12-02T20:59:00Z
---

# init(_:selection:columnCustomization:columns:)

**Initializer**

Creates a table that computes its rows based on a collection of identifiable data, that supports selecting multiple rows, and that has dynamically customizable columns.

## Declaration

```swift
nonisolated init<Data>(_ data: Data, selection: Binding<Set<Value.ID>>, columnCustomization: Binding<TableColumnCustomization<Value>>, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableForEachContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## Parameters

- **data**: The identifiable data for computing the table rows.
- **selection**: A binding to a set that identifies selected rows IDs.
- **columnCustomization**: A binding to the state of columns.
- **columns**: The columns to display in the table.

## Discussion

Each column in the table that should participate in customization is required to have an identifier, specified with [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md).

## Creating a table with customizable columns

- **init(_:columnCustomization:columns:)**: Creates a table that computes its rows based on a collection of identifiable data and has dynamically customizable columns.
- **init(_:selection:sortOrder:columnCustomization:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data, supports selecting multiple rows, and has dynamically customizable columns.
- **init(_:sortOrder:columnCustomization:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data and has dynamically customizable columns.

