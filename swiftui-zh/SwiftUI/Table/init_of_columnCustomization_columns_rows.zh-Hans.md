--- 来源：https://developer.apple.com/documentation/SwiftUI/Table/init(of:columnCustomization:columns:rows:)

抓取时间：2025-12-02T20:59:02Z

---

# init(of:columnCustomization:columns:rows:)

**Initializer**

创建一个具有指定列和行的表格，该表格的内容使用指定类型的值生成，并且列可以动态自定义。

## 声明

```swift
nonisolated init(of valueType: Value.Type, columnCustomization: Binding<TableColumnCustomization<Value>>, @TableColumnBuilder<Value, Never> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows)
```

## 参数

- **valueType**：用于派生表格内容的值的类型。

- **columnCustomization**：列状态的绑定。

- **columns**：要在表格中显示的列。

- **rows**：表格中要显示的行。

## 说明

表格中每个需要进行自定义的列都必须有一个标识符，用 [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md) 指定。

## 创建具有动态可自定义列的表格

- **init(of:selection:columnCustomization:columns:rows:)**：创建一个具有指定列和行的表格，支持选择多行，并使用指定类型的值生成数据，且具有动态可自定义列。

- **init(of:selection:sortOrder:columnCustomization:columns:rows:)**：创建一个具有指定列和行的可排序表格，支持选择多行和动态可自定义列。

- **init(of:sortOrder:columnCustomization:columns:rows:)**：创建一个具有指定列和行的可排序表格，且具有动态可自定义列。


---
source: https://developer.apple.com/documentation/SwiftUI/Table/init(of:columnCustomization:columns:rows:)
crawled: 2025-12-02T20:59:02Z
---

# init(of:columnCustomization:columns:rows:)

**Initializer**

Creates a table with the given columns and rows that generates its contents using values of the given type and has dynamically customizable columns.

## Declaration

```swift
nonisolated init(of valueType: Value.Type, columnCustomization: Binding<TableColumnCustomization<Value>>, @TableColumnBuilder<Value, Never> columns: () -> Columns, @TableRowBuilder<Value> rows: () -> Rows)
```

## Parameters

- **valueType**: The type of value used to derive the table’s contents.
- **columnCustomization**: A binding to the state of columns.
- **columns**: The columns to display in the table.
- **rows**: The rows to display in the table.

## Discussion

Each column in the table that should participate in customization is required to have an identifier, specified with [customizationID(_:)](../TableColumnContent/customizationID.zh-Hans.md).

## Creating a table with dynamically customizable columns

- **init(of:selection:columnCustomization:columns:rows:)**: Creates a table with the given columns and rows that supports selecting multiple rows that generates its data using values of the given type and has dynamically customizable columns.
- **init(of:selection:sortOrder:columnCustomization:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows and dynamically customizable columns.
- **init(of:sortOrder:columnCustomization:columns:rows:)**: Creates a sortable table with the given columns and rows and has dynamically customizable columns.

