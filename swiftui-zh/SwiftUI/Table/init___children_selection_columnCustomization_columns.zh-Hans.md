--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(_:children:selection:columnCustomization:columns:)

抓取时间：2025-12-01T00:43:09Z

---

# init(_:children:selection:columnCustomization:columns:)

**Initializer**

创建一个层级式表格，该表格基于一组可识别数据及其子项的键路径来计算行，并支持选择多行。

## 声明

```swift
nonisolated init<Data>(_ data: Data, children: KeyPath<Data.Element, Data?>, selection: Binding<Set<Value.ID>>, columnCustomization: Binding<TableColumnCustomization<Value>>? = nil, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableOutlineGroupContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## 参数

- **data**：用于计算表格行的可识别数据。

- **children**：指向属性的键路径，该属性的非 `nil` 值表示 `data` 的子项，其 `nil` 值表示层次结构中的叶子行，该叶子行不能拥有子项。

- **selection**：绑定到标识所选行 ID 的集合。

- **columnCustomization**：绑定到列的状态。

- **columns**：要在表中显示的列。

## 讨论

表中每个需要进行自定义的列都必须有一个标识符，使用 [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md) 指定。

## 创建层次结构表

- **init(_:children:columnCustomization:columns:)**：创建一个层次结构表，该表基于一组可识别的数据以及指向该数据子项的键路径来计算其行。

- **init(_:children:selection:sortOrder:columnCustomization:columns:)**：创建一个可排序的层次结构表，该表基于一组可识别的数据以及指向该数据子项的键路径来计算其行，并支持选择多行。

- **init(_:children:sortOrder:columnCustomization:columns:)**：创建一个可排序的层次结构表，该表基于一组可识别的数据以及指向该数据子项的键路径来计算其行。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(_:children:selection:columnCustomization:columns:)
crawled: 2025-12-01T00:43:09Z
---

# init(_:children:selection:columnCustomization:columns:)

**Initializer**

Creates a hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data, and supports selecting multiple rows.

## Declaration

```swift
nonisolated init<Data>(_ data: Data, children: KeyPath<Data.Element, Data?>, selection: Binding<Set<Value.ID>>, columnCustomization: Binding<TableColumnCustomization<Value>>? = nil, @TableColumnBuilder<Value, Never> columns: () -> Columns) where Rows == TableOutlineGroupContent<Data>, Data : RandomAccessCollection, Columns.TableRowValue == Data.Element
```

## Parameters

- **data**: The identifiable data for computing the table rows.
- **children**: A key path to a property whose non-`nil` value gives the children of `data`, and whose `nil` value represents a leaf row of the hierarchy, which is not capable of having children.
- **selection**: A binding to a set that identifies selected rows IDs.
- **columnCustomization**: A binding to the state of columns.
- **columns**: The columns to display in the table.

## Discussion

Each column in the table that should participate in customization is required to have an identifier, specified with [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md).

## Creating a hierarchical table

- **init(_:children:columnCustomization:columns:)**: Creates a hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data.
- **init(_:children:selection:sortOrder:columnCustomization:columns:)**: Creates a sortable, hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data, and supports selecting multiple rows.
- **init(_:children:sortOrder:columnCustomization:columns:)**: Creates a sortable, hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data.

