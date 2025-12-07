--- 来源：https://developer.apple.com/documentation/SwiftUI/Table

抓取时间：2025-12-02T16:15:59Z

---

# 表格

**Structure**

表格是一个容器，用于呈现排列成一列或多列的数据行，并可选择是否提供选择一个或多个成员的功能。

## 声明

```swift
struct Table<Value, Rows, Columns> where Value == Rows.TableRowValue, Rows : TableRowContent, Columns : TableColumnContent, Rows.TableRowValue == Columns.TableRowValue
```

## 概述

表格通常基于数据集合创建。以下示例展示了如何从符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议的 `Person` 实例数组创建一个简单的三列表格：

```swift
struct Person: Identifiable {
    let givenName: String
    let familyName: String
    let emailAddress: String
    let id = UUID()

    var fullName: String { givenName + " " + familyName }
}

@State private var people = [
    Person(givenName: "Juan", familyName: "Chavez", emailAddress: "juanchavez@icloud.com"),
    Person(givenName: "Mei", familyName: "Chen", emailAddress: "meichen@icloud.com"),
    Person(givenName: "Tom", familyName: "Clark", emailAddress: "tomclark@icloud.com"),
    Person(givenName: "Gita", familyName: "Kumar", emailAddress: "gitakumar@icloud.com")
]

struct PeopleTable: View {
    var body: some View {
        Table(people) {
            TableColumn("Given Name", value: \.givenName)
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail Address", value: \.emailAddress)
        }
    }
}
```

如果行数超过可用空间，`Table` 会自动提供垂直滚动。在 macOS 上，如果表格列数超过视图宽度，表格还会提供水平滚动条。滚动条在 iOS 上会根据需要显示；在 macOS 上，滚动条的显示或隐藏取决于“显示滚动条”系统偏好设置。

### 支持表格中的选择

要使表格中的行可选中，请绑定到选择变量。绑定到表格数据的单个实例（例如 DL_0026）会创建一个单选表格。绑定到 DL_0025 会创建一个支持多选的表格。以下示例展示了如何在前面的示例中添加多选功能。表格下方的视图（例如 DL_0024）会显示当前选中的项目数。

```swift
struct SelectableTable: View {
    @State private var selectedPeople = Set<Person.ID>()

    var body: some View {
        Table(people, selection: $selectedPeople) {
            TableColumn("Given Name", value: \.givenName)
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail Address", value: \.emailAddress)
        }
        Text("\(selectedPeople.count) people selected")
    }
}
```

### 支持表格排序

要使表格的列可排序，请提供与 [doc://com.apple.documentation/documentation/Foundation/SortComparator] 实例数组的绑定。表格会通过其列标题反映排序状态，从而允许对任何具有键路径的列进行排序。

当表格排序描述符更新时，重新对表格底层的数据集合进行排序；表格本身不会执行排序操作。您可以使用 [onChange(of:perform:)](View/onChange_of_perform.zh-Hans.md) 修饰符来监视排序描述符的变化，然后在修饰符的 `perform` 闭包中对数据进行排序。

以下示例展示了如何为前面的示例添加排序功能：

```swift
struct SortableTable: View {
    @State private var sortOrder = [KeyPathComparator(\Person.givenName)]

    var body: some View {
        Table(people, sortOrder: $sortOrder) {
            TableColumn("Given Name", value: \.givenName)
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail address", value: \.emailAddress)
        }
        .onChange(of: sortOrder) { _, sortOrder in
            people.sort(using: sortOrder)
        }
    }
}
```

### 使用静态行构建表格

要从静态行（而不是数据集合的内容）创建表格，您需要同时提供列和行。

以下示例展示了一个表格，该表格通过在一组固定价格的基础上应用不同的小费（“小费”）来计算价格。它使用 [init(of:columns:rows:)](Table/init_of_columns_rows.zh-Hans.md) 初始化器创建表格，`rows` 参数提供每行用于计算的基准价格。每一列接收每个价格并执行计算，生成 [Text](Text.zh-Hans.md) 以显示格式化的结果。

```swift
struct Purchase: Identifiable {
    let price: Decimal
    let id = UUID()
}

struct TipTable: View {
    let currencyStyle = Decimal.FormatStyle.Currency(code: "USD")

    var body: some View {
        Table(of: Purchase.self) {
            TableColumn("Base price") { purchase in
                Text(purchase.price, format: currencyStyle)
            }
            TableColumn("With 15% tip") { purchase in
                Text(purchase.price * 1.15, format: currencyStyle)
            }
            TableColumn("With 20% tip") { purchase in
                Text(purchase.price * 1.2, format: currencyStyle)
            }
            TableColumn("With 25% tip") { purchase in
                Text(purchase.price * 1.25, format: currencyStyle)
            }
        } rows: {
            TableRow(Purchase(price: 20))
            TableRow(Purchase(price: 50))
            TableRow(Purchase(price: 75))
        }
    }
}
```

### 表格样式

使用 [tableStyle(_:)](View/tableStyle.zh-Hans.md) 修饰符为视图中的所有表格设置 [TableStyle](TableStyle.zh-Hans.md) 样式。SwiftUI 提供了多种表格样式，例如 [InsetTableStyle](InsetTableStyle.zh-Hans.md) 以及 macOS 上的 [BorderedTableStyle](BorderedTableStyle.zh-Hans.md)。默认样式为 [AutomaticTableStyle](AutomaticTableStyle.zh-Hans.md)，适用于所有支持 `Table` 的平台。

### 在不同平台上使用表格

您可以定义一个表格，用于 macOS、iOS 和 iPadOS。但是，在 iPhone 或紧凑的横向尺寸环境下（例如 iPad 的某些模式，如 Slide Over），表格的列显示空间有限。为了节省空间，表格会在检测到这种情况时自动隐藏标题和第一列之后的所有列。

为了在空间受限的环境中提供良好的用户体验，您可以自定义第一列，使其在检测到 [horizontalSizeClass](EnvironmentValues/horizontalSizeClass.zh-Hans.md) 环境值变为 [compact](UserInterfaceSizeClass/compact.zh-Hans.md) 时显示更多信息。例如，您可以修改上面的可排序表格，使其根据条件显示第一列中的所有信息：

```swift
struct CompactableTable: View {
    #if os(iOS)
    @Environment(\.horizontalSizeClass) private var horizontalSizeClass
    private var isCompact: Bool { horizontalSizeClass == .compact }
    #else
    private let isCompact = false
    #endif

    @State private var sortOrder = [KeyPathComparator(\Person.givenName)]

    var body: some View {
        Table(people, sortOrder: $sortOrder) {
            TableColumn("Given Name", value: \.givenName) { person in
                VStack(alignment: .leading) {
                    Text(isCompact ? person.fullName : person.givenName)
                    if isCompact {
                        Text(person.emailAddress)
                            .foregroundStyle(.secondary)
                    }
                }
            }
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail Address", value: \.emailAddress)
        }
        .onChange(of: sortOrder) { _, sortOrder in
            people.sort(using: sortOrder)
        }
    }
}
```

通过此更改，您可以为较窄的屏幕提供类似列表的外观，同时在较宽的屏幕上显示完整的表格。由于两种情况下都使用相同的表格实例，因此当屏幕尺寸发生变化时（例如用户将应用移入或移出侧滑模式），您可以获得无缝过渡效果。

## 根据列创建表格

- **init(_:columns:)**：创建一个基于可识别数据集合计算行的表格。

- **init(_:selection:columns:)**：创建一个基于可识别数据集合计算行的表格，并支持选择多行。

## 根据列创建可排序表格

- **init(_:sortOrder:columns:)**：创建一个可排序表格，该表格基于一组可识别的数据计算其行。

- **init(_:selection:sortOrder:columns:)**：创建一个可排序表格，该表格基于一组可识别的数据计算其行，并支持选择多行。

## 根据列和行创建表格

- **init(of:columns:rows:)**：创建一个具有给定列和行的表格，该表格使用给定类型的值生成其内容。

- **init(of:selection:columns:rows:)**：创建一个具有给定列和行的表格，该表格支持选择多行，并使用给定类型的值生成其数据。

## 根据列和行创建可排序表格

- **init(of:sortOrder:columns:rows:)**：创建一个具有给定列和行的可排序表格。

- **init(of:selection:sortOrder:columns:rows:)**：创建一个具有指定列和行的可排序表格，支持多行选择。

- **init(sortOrder:columns:rows:)**：创建一个具有指定列和行的可排序表格。

- **init(selection:sortOrder:columns:rows:)**：创建一个具有指定列和行的可排序表格，支持多行选择。

## 创建具有可自定义列的表格

- **init(_:columnCustomization:columns:)**：创建一个基于可识别数据集合计算行数的表格，该表格具有可动态自定义的列。

- **init(_:selection:columnCustomization:columns:)**：创建一个基于可识别数据集合计算行数的表格，支持多行选择，并且具有可动态自定义的列。

- **init(_:selection:sortOrder:columnCustomization:columns:)**：创建一个可排序的表格，该表格基于一组可识别的数据计算其行，支持选择多行，并且具有可动态自定义的列。

- **init(_:sortOrder:columnCustomization:columns:)**：创建一个可排序的表格，该表格基于一组可识别的数据计算其行，并且具有可动态自定义的列。

## 创建具有可动态自定义列的表格

- **init(of:columnCustomization:columns:rows:)**：创建一个具有给定列和行的表格，该表格使用给定类型的值生成其内容，并且具有可动态自定义的列。

- **init(of:selection:columnCustomization:columns:rows:)**：创建一个具有给定列和行的表格，该表格支持选择多行，使用给定类型的值生成其数据，并且具有可动态自定义的列。

- **init(of:selection:sortOrder:columnCustomization:columns:rows:)**：创建一个具有给定列和行的可排序表格，该表格支持选择多行，并且具有可动态自定义的列。

- **init(of:sortOrder:columnCustomization:columns:rows:)**：创建一个具有指定列和行的可排序表格，并且列可以动态自定义。

## 创建层次结构表

- **init(_:children:columnCustomization:columns:)**：创建一个层次结构表，该表基于一组可识别的数据以及指向该数据子项的键路径来计算其行。

- **init(_:children:selection:columnCustomization:columns:)**：创建一个层次结构表，该表基于一组可识别的数据以及指向该数据子项的键路径来计算其行，并支持选择多行。

- **init(_:children:selection:sortOrder:columnCustomization:columns:)**：创建一个可排序的层次结构表，该表基于一组可识别的数据以及指向该数据子项的键路径来计算其行，并支持选择多行。

- **init(_:children:sortOrder:columnCustomization:columns:)**：创建一个可排序的层级表格，该表格的行基于一组可识别的数据以及指向该数据子项的键路径计算得出。

## 创建表格

- **使用 SwiftUI 构建出色的 Mac 应用**：通过集成侧边栏、表格、工具栏和其他一些常用的用户界面元素，创建引人入胜的 SwiftUI Mac 应用。

- **tableStyle(_:)**：设置此视图中表格的样式。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/Table
crawled: 2025-12-02T16:15:59Z
---

# Table

**Structure**

A container that presents rows of data arranged in one or more columns, optionally providing the ability to select one or more members.

## Declaration

```swift
struct Table<Value, Rows, Columns> where Value == Rows.TableRowValue, Rows : TableRowContent, Columns : TableColumnContent, Rows.TableRowValue == Columns.TableRowValue
```

## Overview

You commonly create tables from collections of data. The following example shows how to create a simple, three-column table from an array of `Person` instances that conform to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol:

```swift
struct Person: Identifiable {
    let givenName: String
    let familyName: String
    let emailAddress: String
    let id = UUID()

    var fullName: String { givenName + " " + familyName }
}

@State private var people = [
    Person(givenName: "Juan", familyName: "Chavez", emailAddress: "juanchavez@icloud.com"),
    Person(givenName: "Mei", familyName: "Chen", emailAddress: "meichen@icloud.com"),
    Person(givenName: "Tom", familyName: "Clark", emailAddress: "tomclark@icloud.com"),
    Person(givenName: "Gita", familyName: "Kumar", emailAddress: "gitakumar@icloud.com")
]

struct PeopleTable: View {
    var body: some View {
        Table(people) {
            TableColumn("Given Name", value: \.givenName)
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail Address", value: \.emailAddress)
        }
    }
}
```



If there are more rows than can fit in the available space, `Table` provides vertical scrolling automatically. On macOS, the table also provides horizontal scrolling if there are more columns than can fit in the width of the view. Scroll bars appear as needed on iOS; on macOS, the `Table` shows or hides scroll bars based on the “Show scroll bars” system preference.

### Supporting selection in tables

To make rows of a table selectable, provide a binding to a selection variable. Binding to a single instance of the table data’s [doc://com.apple.documentation/documentation/Swift/Identifiable/id-8t2ws] type creates a single-selection table. Binding to a [doc://com.apple.documentation/documentation/Swift/Set] creates a table that supports multiple selections. The following example shows how to add multi-select to the previous example. A [Text](Text.zh-Hans.md) view below the table shows the number of items currently selected.

```swift
struct SelectableTable: View {
    @State private var selectedPeople = Set<Person.ID>()

    var body: some View {
        Table(people, selection: $selectedPeople) {
            TableColumn("Given Name", value: \.givenName)
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail Address", value: \.emailAddress)
        }
        Text("\(selectedPeople.count) people selected")
    }
}
```

### Supporting sorting in tables

To make the columns of a table sortable, provide a binding to an array of [doc://com.apple.documentation/documentation/Foundation/SortComparator] instances. The table reflects the sorted state through its column headers, allowing sorting for any columns with key paths.

When the table sort descriptors update, re-sort the data collection that underlies the table; the table itself doesn’t perform a sort operation. You can watch for changes in the sort descriptors by using a [onChange(of:perform:)](View/onChange_of_perform.zh-Hans.md) modifier, and then sort the data in the modifier’s `perform` closure.

The following example shows how to add sorting capability to the previous example:

```swift
struct SortableTable: View {
    @State private var sortOrder = [KeyPathComparator(\Person.givenName)]

    var body: some View {
        Table(people, sortOrder: $sortOrder) {
            TableColumn("Given Name", value: \.givenName)
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail address", value: \.emailAddress)
        }
        .onChange(of: sortOrder) { _, sortOrder in
            people.sort(using: sortOrder)
        }
    }
}
```

### Building tables with static rows

To create a table from static rows, rather than the contents of a collection of data, you provide both the columns and the rows.

The following example shows a table that calculates prices from applying varying gratuities (“tips”) to a fixed set of prices. It creates the table with the [init(of:columns:rows:)](Table/init_of_columns_rows.zh-Hans.md) initializer, with the `rows` parameter providing the base price that each row uses for its calculations. Each column receives each price and performs its calculation, producing a [Text](Text.zh-Hans.md) to display the formatted result.

```swift
struct Purchase: Identifiable {
    let price: Decimal
    let id = UUID()
}

struct TipTable: View {
    let currencyStyle = Decimal.FormatStyle.Currency(code: "USD")

    var body: some View {
        Table(of: Purchase.self) {
            TableColumn("Base price") { purchase in
                Text(purchase.price, format: currencyStyle)
            }
            TableColumn("With 15% tip") { purchase in
                Text(purchase.price * 1.15, format: currencyStyle)
            }
            TableColumn("With 20% tip") { purchase in
                Text(purchase.price * 1.2, format: currencyStyle)
            }
            TableColumn("With 25% tip") { purchase in
                Text(purchase.price * 1.25, format: currencyStyle)
            }
        } rows: {
            TableRow(Purchase(price: 20))
            TableRow(Purchase(price: 50))
            TableRow(Purchase(price: 75))
        }
    }
}
```



### Styling tables

Use the [tableStyle(_:)](View/tableStyle.zh-Hans.md) modifier to set a [TableStyle](TableStyle.zh-Hans.md) for all tables within a view. SwiftUI provides several table styles, such as [InsetTableStyle](InsetTableStyle.zh-Hans.md) and, on macOS, [BorderedTableStyle](BorderedTableStyle.zh-Hans.md). The default style is [AutomaticTableStyle](AutomaticTableStyle.zh-Hans.md), which is available on all platforms that support `Table`.

### Using tables on different platforms

You can define a single table for use on macOS, iOS, and iPadOS. However, on iPhone or in a compact horizontal size class environment — typical on iPad in certain modes, like Slide Over — the table has limited space to display its columns. To conserve space, the table automatically hides headers and all columns after the first when it detects this condition.

To provide a good user experience in a space-constrained environment, you can customize the first column to show more information when you detect that the [horizontalSizeClass](EnvironmentValues/horizontalSizeClass.zh-Hans.md) environment value becomes [compact](UserInterfaceSizeClass/compact.zh-Hans.md). For example, you can modify the sortable table from above to conditionally show all the information in the first column:

```swift
struct CompactableTable: View {
    #if os(iOS)
    @Environment(\.horizontalSizeClass) private var horizontalSizeClass
    private var isCompact: Bool { horizontalSizeClass == .compact }
    #else
    private let isCompact = false
    #endif

    @State private var sortOrder = [KeyPathComparator(\Person.givenName)]

    var body: some View {
        Table(people, sortOrder: $sortOrder) {
            TableColumn("Given Name", value: \.givenName) { person in
                VStack(alignment: .leading) {
                    Text(isCompact ? person.fullName : person.givenName)
                    if isCompact {
                        Text(person.emailAddress)
                            .foregroundStyle(.secondary)
                    }
                }
            }
            TableColumn("Family Name", value: \.familyName)
            TableColumn("E-Mail Address", value: \.emailAddress)
        }
        .onChange(of: sortOrder) { _, sortOrder in
            people.sort(using: sortOrder)
        }
    }
}
```

By making this change, you provide a list-like appearance for narrower displays, while displaying the full table on wider ones. Because you use the same table instance in both cases, you get a seamless transition when the size class changes, like when someone moves your app into or out of Slide Over.

## Creating a table from columns

- **init(_:columns:)**: Creates a table that computes its rows based on a collection of identifiable data.
- **init(_:selection:columns:)**: Creates a table that computes its rows based on a collection of identifiable data, and that supports selecting multiple rows.

## Creating a sortable table from columns

- **init(_:sortOrder:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data.
- **init(_:selection:sortOrder:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data, and supports selecting multiple rows.

## Creating a table from columns and rows

- **init(of:columns:rows:)**: Creates a table with the given columns and rows that generates its contents using values of the given type.
- **init(of:selection:columns:rows:)**: Creates a table with the given columns and rows that supports selecting multiple rows that generates its data using values of the given type.

## Creating a sortable table from columns and rows

- **init(of:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows.
- **init(of:selection:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows.
- **init(sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows.
- **init(selection:sortOrder:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows.

## Creating a table with customizable columns

- **init(_:columnCustomization:columns:)**: Creates a table that computes its rows based on a collection of identifiable data and has dynamically customizable columns.
- **init(_:selection:columnCustomization:columns:)**: Creates a table that computes its rows based on a collection of identifiable data, that supports selecting multiple rows, and that has dynamically customizable columns.
- **init(_:selection:sortOrder:columnCustomization:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data, supports selecting multiple rows, and has dynamically customizable columns.
- **init(_:sortOrder:columnCustomization:columns:)**: Creates a sortable table that computes its rows based on a collection of identifiable data and has dynamically customizable columns.

## Creating a table with dynamically customizable columns

- **init(of:columnCustomization:columns:rows:)**: Creates a table with the given columns and rows that generates its contents using values of the given type and has dynamically customizable columns.
- **init(of:selection:columnCustomization:columns:rows:)**: Creates a table with the given columns and rows that supports selecting multiple rows that generates its data using values of the given type and has dynamically customizable columns.
- **init(of:selection:sortOrder:columnCustomization:columns:rows:)**: Creates a sortable table with the given columns and rows that supports selecting multiple rows and dynamically customizable columns.
- **init(of:sortOrder:columnCustomization:columns:rows:)**: Creates a sortable table with the given columns and rows and has dynamically customizable columns.

## Creating a hierarchical table

- **init(_:children:columnCustomization:columns:)**: Creates a hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data.
- **init(_:children:selection:columnCustomization:columns:)**: Creates a hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data, and supports selecting multiple rows.
- **init(_:children:selection:sortOrder:columnCustomization:columns:)**: Creates a sortable, hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data, and supports selecting multiple rows.
- **init(_:children:sortOrder:columnCustomization:columns:)**: Creates a sortable, hierarchical table that computes its rows based on a collection of identifiable data and key path to the children of that data.

## Creating a table

- **Building a great Mac app with SwiftUI**: Create engaging SwiftUI Mac apps by incorporating side bars, tables, toolbars, and several other popular user interface elements.
- **tableStyle(_:)**: Sets the style for tables within this view.

## Conforms To

- View

