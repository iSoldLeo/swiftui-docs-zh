---
来源： https://developer.apple.com/documentation/swiftui/tablecolumncontent
抓取时间： 2025-12-04T13:36:50Z
---

# TableColumnContent

**Protocol**

用于表示表格中列的类型。

### 声明

```swift
@MainActor @preconcurrency protocol TableColumnContent<TableRowValue, TableColumnSortComparator>
```

## 概览

该类型提供列的主体内容、列的行值类型以及用于对行进行排序的比较器。

您可以将列内容分解为单独的类型或属性，或创建符合`TableColumnContent`的自定义类型。

```swift
var body: some View {
    Table(people, selection: $selectedPeople, sortOrder: $sortOrder) {
        nameColumns

        TableColumn("Location", value: \.location) {
            LocationView($0.location)
        }
    }
}

@TableColumnBuilder<Person, KeyPathComparator<Person>>
private var nameColumns: some TableColumnContent<
    Person, KeyPathComparator<Person>
> {
    TableColumn("First Name", value: \.firstName) {
        PrimaryColumnView(person: $0)
    }
    TableColumn("Last Name", value: \.lastName)
    TableColumn("Nickname", value: \.nickname)
}
```

上面的示例将三个表列合并为一个单独的计算属性，该属性具有不透明类型。该属性的主要关联类型`TableRowValue` 是`Person`，其关联类型`TableColumnSortComparator` 是`Person` 类型的键比较器。

如果符合本协议的`@preconcurrency @MainActor`类型的基本声明中包含了符合本协议的`@preconcurrency @MainActor`隔离，则该类型将继承本协议的`@preconcurrency @MainActor`隔离：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取列主体

- **tableColumnBody**：构成表格列内容的内容组成。
- **TableColumnBody**：表示该表格列内容主体的内容类型。

## 定义行值

- **TableRowValue**：该列内容显示的行值类型。

## 定义比较器

- **TableColumnSortComparator**：与此表格列内容相关的排序比较器类型。

## 配置内容

- **alignment(_:)**：设置列的对齐方式，同时适用于列标题标签和该列的行视图内容。
- **customizationID(_:)**：使用`TableColumnCustomization`持久化列状态时，设置与列相关联的标识符。
- **defaultVisibility(_:)**：设置表列的默认可见性。
- **disabledCustomizationBehavior(_:)**：设置表列的默认可见性：设置表列的禁用自定义行为。

## 创建列

- **TableColumn**：为表格中的每一行显示视图的列。
- **TableColumnAlignment**：描述表格列内容的对齐方式。
- **TableColumnBuilder**：从闭包创建表格列内容的结果生成器。
- **TableColumnForEach**：一种结构，可根据需要从底层标识数据集合中计算列。

## 符合类型

- 组
- 表列
- TableColumnForEach
- TupleTableColumnContent


---
source: https://developer.apple.com/documentation/swiftui/tablecolumncontent
crawled: 2025-12-04T13:36:50Z
---

# TableColumnContent

**Protocol**

A type used to represent columns within a table.

## Declaration

```swift
@MainActor @preconcurrency protocol TableColumnContent<TableRowValue, TableColumnSortComparator>
```

## Overview

This type provides the body content of the column, as well as the types of the column’s row values and the comparator used to sort rows.

You can factor column content out into separate types or properties, or by creating a custom type conforming to `TableColumnContent`.

```swift
var body: some View {
    Table(people, selection: $selectedPeople, sortOrder: $sortOrder) {
        nameColumns

        TableColumn("Location", value: \.location) {
            LocationView($0.location)
        }
    }
}

@TableColumnBuilder<Person, KeyPathComparator<Person>>
private var nameColumns: some TableColumnContent<
    Person, KeyPathComparator<Person>
> {
    TableColumn("First Name", value: \.firstName) {
        PrimaryColumnView(person: $0)
    }
    TableColumn("Last Name", value: \.lastName)
    TableColumn("Nickname", value: \.nickname)
}
```

The above example factors three table columns into a separate computed property that has an opaque type. The property’s primary associated type `TableRowValue` is a `Person` and its associated type `TableColumnSortComparator` is a key comparator for the `Person` type.

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting the column body

- **tableColumnBody**: The composition of content that comprise the table column content.
- **TableColumnBody**: The type of content representing the body of this table column content.

## Defining the row value

- **TableRowValue**: The type of value of rows presented by this column content.

## Defining the comparator

- **TableColumnSortComparator**: The type of sort comparator associated with this table column content.

## Configuring the content

- **alignment(_:)**: Sets the alignment of the column, applying to both its column header label and the row view content for that column.
- **customizationID(_:)**: Sets the identifier to be associated with a column when persisting its state with `TableColumnCustomization`.
- **defaultVisibility(_:)**: Sets the default visibility of a table column.
- **disabledCustomizationBehavior(_:)**: Sets the disabled customization behavior for a table column.

## Creating columns

- **TableColumn**: A column that displays a view for each row in a table.
- **TableColumnAlignment**: Describes the alignment of the content of a table column.
- **TableColumnBuilder**: A result builder that creates table column content from closures.
- **TableColumnForEach**: A structure that computes columns on demand from an underlying collection of identified data.

## Conforming Types

- Group
- TableColumn
- TableColumnForEach
- TupleTableColumnContent

