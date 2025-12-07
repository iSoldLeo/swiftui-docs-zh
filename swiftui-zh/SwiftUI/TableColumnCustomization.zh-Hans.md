--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnCustomization
抓取时间：2025-12-02T17:02:56Z

---

# TableColumnCustomization

**Structure**

表格列状态的表示。

## 声明

```swift
struct TableColumnCustomization<RowValue> where RowValue : Identifiable
```

## 概述

`TableColumnCustomization` 可以创建并提供给表格，以启用列的重新排序和列的可见性。可以通过编程方式查询和更新状态，也可以绑定到持久化的应用程序或场景存储。

```swift
struct BugReportTable: View {
    @ObservedObject var dataModel: DataModel
    @Binding var selectedBugReports: Set<BugReport.ID>

    @SceneStorage("BugReportTableConfig")
    private var columnCustomization: TableColumnCustomization<BugReport>

    var body: some View {
        Table(dataModel.bugReports, selection: $selectedBugReports,
            sortOrder: $dataModel.sortOrder,
            columnCustomization: $columnCustomization
        ) {
            TableColumn("Title", value: \.title)
                .customizationID("title")
            TableColumn("ID", value: \.id) {
                Link("\($0.id)", destination: $0.url)
            }
            .customizationID("id")
            TableColumn("Number of Reports", value: \.duplicateCount) {
                Text($0.duplicateCount, format: .number)
            }
            .customizationID("duplicates")
        }
    }
}
```

上面的示例创建了一个包含三列的表格。在 macOS 上，应用程序用户可以重新排序或隐藏和显示这些列。它们的配置将通过“BugReportTableConfig”场景存储标识符保存，并在应用程序重新启动时随窗口一起恢复。

特定列的状态是相对于其自定义标识符存储的，该标识符使用[customizationID(_:)](TableColumnContent/customizationID.zh-Hans.md)修饰符的值。列自定义进行编码和解码时，它依赖于稳定的标识符来恢复与特定列关联的已保存状态。如果表格列没有自定义标识符，则无法对其进行自定义。

这些标识符还可以用于以编程方式更改列自定义，例如以编程方式隐藏列：

```swift
columnCustomization[visibility: "duplicates"] = .hidden
```

通过绑定到整体自定义，可以使用相同的下标语法访问绑定到列可见性：

```swift
struct BugReportTable: View {
    @SceneStorage("BugReportTableConfig")
    private var columnCustomization: TableColumnCustomization<BugReport>

    var body: some View {
        ...
        MyVisibilityView($columnCustomization[visibility: "duplicates"])
    }
}

struct MyVisibilityView: View {
    @Binding var visibility: Visibility
    ...
}
```

## 创建表格列自定义

- **init()**：创建一个空的表格列自定义。

## 管理自定义设置

- **resetOrder()**：将列顺序重置为默认值，同时保留自定义的可见性和大小。

- **subscript(visibility:)**：设置列的可见性，该列由其标识符标识。

## 自定义列

- **tableColumnHeaders(_:)**：控制 `Table` 列标题视图的可见性。

- **TableColumnCustomizationBehavior**：表格可以向用户提供的一组列自定义行为。

## 符合以下标准

- Decodable

- Encodable

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnCustomization
crawled: 2025-12-02T17:02:56Z
---

# TableColumnCustomization

**Structure**

A representation of the state of the columns in a table.

## Declaration

```swift
struct TableColumnCustomization<RowValue> where RowValue : Identifiable
```

## Overview

`TableColumnCustomization` can be created and provided to a table to enable column reordering and column visibility. The state can be queried and updated programmatically, as well as bound to persistent app or scene storage.

```swift
struct BugReportTable: View {
    @ObservedObject var dataModel: DataModel
    @Binding var selectedBugReports: Set<BugReport.ID>

    @SceneStorage("BugReportTableConfig")
    private var columnCustomization: TableColumnCustomization<BugReport>

    var body: some View {
        Table(dataModel.bugReports, selection: $selectedBugReports,
            sortOrder: $dataModel.sortOrder,
            columnCustomization: $columnCustomization
        ) {
            TableColumn("Title", value: \.title)
                .customizationID("title")
            TableColumn("ID", value: \.id) {
                Link("\($0.id)", destination: $0.url)
            }
            .customizationID("id")
            TableColumn("Number of Reports", value: \.duplicateCount) {
                Text($0.duplicateCount, format: .number)
            }
            .customizationID("duplicates")
        }
    }
}
```

The above example creates a table with three columns. On macOS, these columns can be reordered or hidden and shown by the user of the app. Their configuration will be saved and restored with the window on relaunches of the app, using the “BugReportTableConfig” scene storage identifier.

The state of a specific column is stored relative to its customization identifier, using using the value from the [customizationID(_:)](TableColumnContent/customizationID.zh-Hans.md) modifier. When column customization is encoded and decoded, it relies on stable identifiers to restore the associate the saved state with a specific column. If a table column does not have a customization identifier, it will not be customizable.

These identifiers can also be used to programmatically change column customizations, such as programmatically hiding a column:

```swift
columnCustomization[visibility: "duplicates"] = .hidden
```

With a binding to the overall customization, a binding to the visibility of a column can be accessed using the same subscript syntax:

```swift
struct BugReportTable: View {
    @SceneStorage("BugReportTableConfig")
    private var columnCustomization: TableColumnCustomization<BugReport>

    var body: some View {
        ...
        MyVisibilityView($columnCustomization[visibility: "duplicates"])
    }
}

struct MyVisibilityView: View {
    @Binding var visibility: Visibility
    ...
}
```

## Creating a table column customization

- **init()**: Creates an empty table column customization.

## Managing the customization

- **resetOrder()**: Resets the column order back to the default, preserving the customized visibility and size.
- **subscript(visibility:)**: The visibility of the column identified by its identifier.

## Customizing columns

- **tableColumnHeaders(_:)**: Controls the visibility of a `Table`’s column header views.
- **TableColumnCustomizationBehavior**: A set of customization behaviors of a column that a table can offer to a user.

## Conforms To

- Decodable
- Encodable
- Equatable
- Sendable
- SendableMetatype

