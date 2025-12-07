--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(of:selection:sortOrder:columnCustomization:columns:rows:)

抓取时间：2025-12-02T20:59:04Z

---

# init(of:selection:sortOrder:columnCustomization:columns:rows:)

**Initializer**

创建一个具有指定列和行的可排序表格，支持选择多行和动态自定义列。

## 声明

```swift
nonisolated init<Sort>(of valueType: Value.Type = Value.self, selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, columnCustomization: Binding<TableColumnCustomization<Value>>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## 参数

- **valueType**：用于派生表格内容的值类型。

- **selection**：绑定到标识所选行 ID 的集合。

- **sortOrder**：绑定到列的排序顺序。

- **columnCustomization**：绑定到列的状态。

- **columns**：要在表格中显示的列。

- **rows**：要在表格中显示的行。

## 讨论

表格中每个需要进行自定义的列都必须有一个标识符，使用 [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md) 指定。

## 创建具有动态可自定义列的表格

- **init(of:columnCustomization:columns:rows:)**：创建一个具有给定列和行的表格，该表格使用给定类型的值生成其内容，并且具有动态可自定义的列。

- **init(of:selection:columnCustomization:columns:rows:)**：创建一个具有指定列和行的表格，支持选择多行，并使用指定类型的值生成数据，且列可动态自定义。

- **init(of:sortOrder:columnCustomization:columns:rows:)**：创建一个具有指定列和行的可排序表格，且列可动态自定义。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(of:selection:sortOrder:columnCustomization:columns:rows:)
crawled: 2025-12-02T20:59:04Z
---

# init(of:selection:sortOrder:columnCustomization:columns:rows:)

**Initializer**

Creates a sortable table with the given columns and rows that supports selecting multiple rows and dynamically customizable columns.

## Declaration

```swift
nonisolated init<Sort>(of valueType: Value.Type = Value.self, selection: Binding<Set<Value.ID>>, sortOrder: Binding<[Sort]>, columnCustomization: Binding<TableColumnCustomization<Value>>, @TableColumnBuilder<Value, Sort> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows) where Sort : SortComparator, Columns.TableRowValue == Sort.Compared
```

## Parameters

- **valueType**: The type of value used to derive the table’s contents.
- **selection**: A binding to a set that identifies selected rows ids.
- **sortOrder**: A binding to the ordered sorting of columns.
- **columnCustomization**: A binding to the state of columns.
- **columns**: The columns to display in the table.
- **rows**: The rows to display in the table.

## Discussion

Each column in the table that should participate in customization is required to have an identifier, specified with [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md).

## Creating a table with dynamically customizable columns

- **init(of:columnCustomization:columns:rows:)**: Creates a table with the given columns and rows that generates its contents using values of the given type and has dynamically customizable columns.
- **init(of:selection:columnCustomization:columns:rows:)**: Creates a table with the given columns and rows that supports selecting multiple rows that generates its data using values of the given type and has dynamically customizable columns.
- **init(of:sortOrder:columnCustomization:columns:rows:)**: Creates a sortable table with the given columns and rows and has dynamically customizable columns.

