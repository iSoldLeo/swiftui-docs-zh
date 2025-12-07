---
来源： https://developer.apple.com/documentation/SwiftUI/TableRowContent
抓取时间：2025-12-02T17:40:00Z
---

# TableRowContent

**Protocol**

用于表示表格行的类型。

### 声明

```swift
@MainActor @preconcurrency protocol TableRowContent<TableRowValue>
```

## 概览

与[View](View.zh-Hans.md) 协议一样，通过声明符合`TableRowContent` 协议的类型并实现所需的[tableRowBody-swift.property](TableRowContent/tableRowBody-swift_property.zh-Hans.md) 属性，可以创建自定义表行内容。

```swift
struct GroupOfPeopleRows: TableRowContent {
    @Binding var people: [Person]

    var tableRowBody: some TableRowContent<Person> {
        ForEach(people) { person in
            TableRow(person)
                .itemProvider { person.itemProvider }
        }
        .dropDestination(for: Person.self) { destination, newPeople in
            people.insert(contentsOf: newPeople, at: destination)
        }
    }
}
```

此示例使用了不透明结果类型，并指定`TableRowValue` 属性的主要关联类型`tableRowBody` 是`Person`。由此，SwiftUI 可以推断`TableRowValue` 结构的`GroupOfPeopleRows` 也是`Person`。

如果符合本协议的类型在其基本声明中包含了本协议，则该类型将继承`@preconcurrency @MainActor`隔离协议：

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

## 获取行主体

- **tableRowBody**：构成表格行内容的内容组成。
- **TableRowBody**：表示该表格行内容主体的内容类型。

## 定义行值

- **TableRowValue**：表格行内容所代表的值类型。

## 管理交互

- **draggable(_:)**：将此行激活为拖放操作的来源。
- **dropDestination(for:action:)**：将整行定义为拖放操作的目标行，该操作使用您指定的闭包处理拖放的内容。
- **onHover(perform:)**：添加指针移动到整行或离开整行时要执行的操作。
- **itemProvider(_:)**：提供为特定数据元素提供拖动表示的闭包。
- **ItemProviderTableRowModifier**：表行修饰符，用于将项目提供者与某些基本行内容关联起来。

## 为行添加上下文菜单

- **contextMenu(menuItems:)**：为表格行添加上下文菜单。
- **contextMenu(menuItems:preview:)**：为表格行添加带预览的上下文菜单。

### 实例方法

- **selectionDisabled(_:)**：添加控制用户是否可以选择该行的条件。

## 创建行

- **TableRow**：表示表中数据值的行。
- **TableHeaderRowContent**：显示单一视图而非分栏内容的表格行。
- **TupleTableRowContent**：一种表格列内容类型，可创建由 Swift 表格行元组创建的表格行。
- **TableForEachContent**：表行内容类型，用于创建通过遍历集合创建的表行。
- **EmptyTableRowContent**：不产生任何行的表行内容。
- **DynamicTableRowContent**：从底层数据集合生成表行的一种表行内容。
- **TableRowBuilder**：从闭包创建表格行内容的结果生成器。

## 继承自

- 动态表行内容

## 符合类型

- DisclosureTableRow
- 空表格行内容
- ForEach
- 组
- 修改内容
- 大纲组
- 章节
- TableForEachContent
- 表格标题行内容
- 表格大纲组内容
- 表格行
- TupleTableRowContent


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowContent
crawled: 2025-12-02T17:40:00Z
---

# TableRowContent

**Protocol**

A type used to represent table rows.

## Declaration

```swift
@MainActor @preconcurrency protocol TableRowContent<TableRowValue>
```

## Overview

Like with the [View](View.zh-Hans.md) protocol, you can create custom table row content by declaring a type that conforms to the `TableRowContent` protocol and implementing the required [tableRowBody-swift.property](TableRowContent/tableRowBody-swift_property.zh-Hans.md) property.

```swift
struct GroupOfPeopleRows: TableRowContent {
    @Binding var people: [Person]

    var tableRowBody: some TableRowContent<Person> {
        ForEach(people) { person in
            TableRow(person)
                .itemProvider { person.itemProvider }
        }
        .dropDestination(for: Person.self) { destination, newPeople in
            people.insert(contentsOf: newPeople, at: destination)
        }
    }
}
```

This example uses an opaque result type and specifies that the primary associated type `TableRowValue` for the `tableRowBody` property is a `Person`. From this, SwiftUI can infer `TableRowValue` for the `GroupOfPeopleRows` structure is also `Person`.

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

## Getting the row body

- **tableRowBody**: The composition of content that comprise the table row content.
- **TableRowBody**: The type of content representing the body of this table row content.

## Defining the row value

- **TableRowValue**: The type of value represented by this table row content.

## Managing interaction

- **draggable(_:)**: Activates this row as the source of a drag and drop operation.
- **dropDestination(for:action:)**: Defines the entire row as a destination of a drag and drop operation that handles the dropped content with a closure that you specify.
- **onHover(perform:)**: Adds an action to perform when the pointer moves onto or away from the entire row.
- **itemProvider(_:)**: Provides a closure that vends the drag representation for a particular data element.
- **ItemProviderTableRowModifier**: A table row modifier that associates an item provider with some base row content.

## Adding a context menu to a row

- **contextMenu(menuItems:)**: Adds a context menu to a table row.
- **contextMenu(menuItems:preview:)**: Adds a context menu with a preview to a table row.

## Instance Methods

- **selectionDisabled(_:)**: Adds a condition that controls whether users can select this row.

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Inherited By

- DynamicTableRowContent

## Conforming Types

- DisclosureTableRow
- EmptyTableRowContent
- ForEach
- Group
- ModifiedContent
- OutlineGroup
- Section
- TableForEachContent
- TableHeaderRowContent
- TableOutlineGroupContent
- TableRow
- TupleTableRowContent

