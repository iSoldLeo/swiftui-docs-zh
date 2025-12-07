--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitView
抓取时间：2025-12-02T16:15:48Z

---

# NavigationSplitView

**Structure**

导航拆分视图以两列或三列的形式呈现信息，用户在前一列中选择的内容将控制后续列的显示方式。

## 声明

```swift
struct NavigationSplitView<Sidebar, Content, Detail> where Sidebar : View, Content : View, Detail : View
```

## 概述

您可以创建一个两列或三列的导航拆分视图，通常将其用作 [Scene](Scene.zh-Hans.md) 中的根视图。用户在前一列中选择一个或多个项目，即可在后续列中查看这些项目的详细信息。

要创建两列导航拆分视图，请使用 [init(sidebar:detail:)](NavigationSplitView/init_sidebar_detail.zh-Hans.md) 初始化器：

```swift
@State private var employeeIds: Set<Employee.ID> = []

var body: some View {
    NavigationSplitView {
        List(model.employees, selection: $employeeIds) { employee in
            Text(employee.name)
        }
    } detail: {
        EmployeeDetails(for: employeeIds)
    }
}
```

在上面的示例中，导航拆分视图与其第一列中的 [List](List.zh-Hans.md) 相关联，因此当用户进行选择时，详细信息视图会相应更新。您对选择属性所做的任何程序化更改也会同时影响列表外观和显示的详细信息视图。

要创建三列视图，请使用 [init(sidebar:content:detail:)](NavigationSplitView/init_sidebar_content_detail.zh-Hans.md) 初始化器。第一列中的选择会影响第二列，第二列中的选择会影响第三列。例如，您可以显示部门列表、所选部门中的员工列表以及所有所选员工的详细信息：

```swift
@State private var departmentId: Department.ID? // Single selection.
@State private var employeeIds: Set<Employee.ID> = [] // Multiple selection.

var body: some View {
    NavigationSplitView {
        List(model.departments, selection: $departmentId) { department in
            Text(department.name)
        }
    } content: {
        if let department = model.department(id: departmentId) {
            List(department.employees, selection: $employeeIds) { employee in
                Text(employee.name)
            }
        } else {
            Text("Select a department")
        }
    } detail: {
        EmployeeDetails(for: employeeIds)
    }
}
```

您还可以将 [NavigationStack](NavigationStack.zh-Hans.md) 嵌入到列中。点击或单击前面列中出现的 [NavigationLink](NavigationLink.zh-Hans.md) 会设置堆栈在其根视图之上显示的视图。激活同一列中的链接会将视图添加到堆栈中。无论哪种方式，链接必须包含堆栈中具有相应 [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) 修饰符的数据类型。

在 watchOS 和 tvOS 上，以及在 iPhone 或 iPad 等屏幕尺寸较小的设备上使用侧拉功能时，导航分屏视图会将所有列折叠成一个堆栈，并显示最后一列的有用信息。例如，上面的三列示例会显示初始部门列表、用户选择部门后该部门的员工列表，以及用户选择员工后该员工的详细信息。对于列表中包含 [NavigationLink](NavigationLink.zh-Hans.md) 实例的行，列表在折叠状态下会显示展开箭头。

### 控制列可见性

您可以通过创建类型为 [NavigationSplitViewVisibility](NavigationSplitViewVisibility.zh-Hans.md) 的 [State](State.zh-Hans.md) 值，以编程方式控制导航拆分视图列的可见性。然后将 [Binding](Binding.zh-Hans.md) 传递给该状态的相应初始化器——例如，两列使用 [init(columnVisibility:sidebar:detail:)](NavigationSplitView/init_columnVisibility_sidebar_detail.zh-Hans.md)，三列使用 [init(columnVisibility:sidebar:content:detail:)](NavigationSplitView/init_columnVisibility_sidebar_content_detail.zh-Hans.md)。

以下代码更新了上面的第一个示例，使其在视图出现时始终隐藏第一列：

```swift
@State private var employeeIds: Set<Employee.ID> = []
@State private var columnVisibility =
    NavigationSplitViewVisibility.detailOnly

var body: some View {
    NavigationSplitView(columnVisibility: $columnVisibility) {
        List(model.employees, selection: $employeeIds) { employee in
            Text(employee.name)
        }
    } detail: {
        EmployeeDetails(for: employeeIds)
    }
}
```

当拆分视图将其列折叠成一个堆栈时，它会忽略可见性控制。

### 折叠的拆分视图

在 iPhone 或 Apple Watch 等尺寸较小的设备上，导航拆分视图会折叠成一个堆栈。通常，SwiftUI 会根据拆分视图列的内容自动选择要显示在该堆栈顶部的视图。

对于自定义导航体验，您可以提供更多信息来帮助 SwiftUI 选择正确的列。创建一个类型为 [NavigationSplitViewColumn](NavigationSplitViewColumn.zh-Hans.md) 的 `State` 值。然后将 `Binding` 传递给该状态的相应初始化器，例如 [init(preferredCompactColumn:sidebar:detail:)](NavigationSplitView/init_preferredCompactColumn_sidebar_detail.zh-Hans.md) 或 [init(preferredCompactColumn:sidebar:content:detail:)](NavigationSplitView/init_preferredCompactColumn_sidebar_content_detail.zh-Hans.md)。

以下代码在 iPhone 上运行时显示蓝色详情视图。当用户点击应用返回按钮时，他们将看到黄色视图。`preferredPreferredCompactColumn` 的值将从 `.detail` 变为 `.sidebar`：

```swift
@State private var preferredColumn =
    NavigationSplitViewColumn.detail

var body: some View {
    NavigationSplitView(preferredCompactColumn: $preferredColumn) {
        Color.yellow
    } detail: {
        Color.blue
    }
}
```

### 自定义分屏视图

要在导航分屏视图中指定首选列宽，请使用 [navigationSplitViewColumnWidth(_:)](View/navigationSplitViewColumnWidth.zh-Hans.md) 修饰符。要设置列的最小、最大和理想尺寸，请使用 [navigationSplitViewColumnWidth(min:ideal:max:)](View/navigationSplitViewColumnWidth_min_ideal_max.zh-Hans.md)。您可以为每一列指定不同的修饰符。导航拆分视图会尽力适应您指定的偏好设置，但可能会根据其他约束条件进行调整。

要指定导航拆分视图中各列的交互方式，请使用 [navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md) 修饰符并设置 [NavigationSplitViewStyle](NavigationSplitViewStyle.zh-Hans.md) 值。例如，您可以指定是突出显示详细信息列，还是使所有列具有相同的突出显示度。

在某些平台上，`NavigationSplitView` 会添加一个 [sidebarToggle](ToolbarDefaultItemKind/sidebarToggle.zh-Hans.md) 工具栏项。使用 [toolbar(removing:)](View/toolbar_removing.zh-Hans.md) 修饰符可以移除默认的工具栏项。

## 创建导航拆分视图

- **init(sidebar:detail:)**：创建一个双列导航拆分视图。

- **init(sidebar:content:detail:)**：创建三列导航拆分视图。

## 隐藏导航拆分视图中的列

- **init(columnVisibility:sidebar:detail:)**：创建两列导航拆分视图，允许通过编程方式控制侧边栏的可见性。

- **init(columnVisibility:sidebar:content:detail:)**：创建三列导航拆分视图，允许通过编程方式控制前导列的可见性。

## 指定首选的紧凑列

- **init(preferredCompactColumn:sidebar:detail:)**：创建两列导航拆分视图，允许通过编程方式控制在窄尺寸下视图折叠成单列时，哪一列显示在最上面。

- **init(preferredCompactColumn:sidebar:content:detail:)**：创建三列导航拆分视图，允许通过编程方式控制在窄尺寸下视图折叠成单列时，哪一列显示在最上面。

## 指定首选的紧凑列和列可见性

- **init(columnVisibility:preferredCompactColumn:sidebar:detail:)**：创建一个双列导航拆分视图，允许以编程方式控制常规尺寸下侧边栏的可见性，以及在窄尺寸下视图折叠成单列时哪一列显示在最上面。

- **init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)**：创建一个三列导航拆分视图，允许以编程方式控制常规尺寸下前导列的可见性，以及在窄尺寸下视图折叠成单列时哪一列显示在最上面。

## 以列的形式呈现视图

- **为您的 SwiftUI 应用带来强大的导航结构**：使用导航链接、堆栈、目标和路径，为所有平台提供流畅的体验，以及深度链接和状态恢复等功能。

- **迁移到新的导航类型**：通过将导航视图替换为导航堆栈和导航拆分视图，改进应用中的导航行为。

- **navigationSplitViewStyle(_:)**：设置此视图内导航拆分视图的样式。

- **navigationSplitViewColumnWidth(_:)**：设置包含此视图的列的固定首选宽度。

- **navigationSplitViewColumnWidth(min:ideal:max:)**：设置包含此视图的列的灵活首选宽度。

- **NavigationSplitViewVisibility**：导航拆分视图中前导列的可见性。

- **NavigationLink**：控制导航呈现方式的视图。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView
crawled: 2025-12-02T16:15:48Z
---

# NavigationSplitView

**Structure**

A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.

## Declaration

```swift
struct NavigationSplitView<Sidebar, Content, Detail> where Sidebar : View, Content : View, Detail : View
```

## Overview

You create a navigation split view with two or three columns, and typically use it as the root view in a [Scene](Scene.zh-Hans.md). People choose one or more items in a leading column to display details about those items in subsequent columns.

To create a two-column navigation split view, use the [init(sidebar:detail:)](NavigationSplitView/init_sidebar_detail.zh-Hans.md) initializer:

```swift
@State private var employeeIds: Set<Employee.ID> = []

var body: some View {
    NavigationSplitView {
        List(model.employees, selection: $employeeIds) { employee in
            Text(employee.name)
        }
    } detail: {
        EmployeeDetails(for: employeeIds)
    }
}
```

In the above example, the navigation split view coordinates with the [List](List.zh-Hans.md) in its first column, so that when people make a selection, the detail view updates accordingly. Programmatic changes that you make to the selection property also affect both the list appearance and the presented detail view.

To create a three-column view, use the [init(sidebar:content:detail:)](NavigationSplitView/init_sidebar_content_detail.zh-Hans.md) initializer. The selection in the first column affects the second, and the selection in the second column affects the third. For example, you can show a list of departments, the list of employees in the selected department, and the details about all of the selected employees:

```swift
@State private var departmentId: Department.ID? // Single selection.
@State private var employeeIds: Set<Employee.ID> = [] // Multiple selection.

var body: some View {
    NavigationSplitView {
        List(model.departments, selection: $departmentId) { department in
            Text(department.name)
        }
    } content: {
        if let department = model.department(id: departmentId) {
            List(department.employees, selection: $employeeIds) { employee in
                Text(employee.name)
            }
        } else {
            Text("Select a department")
        }
    } detail: {
        EmployeeDetails(for: employeeIds)
    }
}
```

You can also embed a [NavigationStack](NavigationStack.zh-Hans.md) in a column. Tapping or clicking a [NavigationLink](NavigationLink.zh-Hans.md) that appears in an earlier column sets the view that the stack displays over its root view. Activating a link in the same column adds a view to the stack. Either way, the link must present a data type for which the stack has a corresponding [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) modifier.

On watchOS and tvOS, and with narrow sizes like on iPhone or on iPad in Slide Over, the navigation split view collapses all of its columns into a stack, and shows the last column that displays useful information. For example, the three-column example above shows the list of departments to start, the employees in the department after someone selects a department, and the employee details when someone selects an employee. For rows in a list that have [NavigationLink](NavigationLink.zh-Hans.md) instances, the list draws disclosure chevrons while in the collapsed state.

### Control column visibility

You can programmatically control the visibility of navigation split view columns by creating a [State](State.zh-Hans.md) value of type [NavigationSplitViewVisibility](NavigationSplitViewVisibility.zh-Hans.md). Then pass a [Binding](Binding.zh-Hans.md) to that state to the appropriate initializer — such as [init(columnVisibility:sidebar:detail:)](NavigationSplitView/init_columnVisibility_sidebar_detail.zh-Hans.md) for two columns, or the [init(columnVisibility:sidebar:content:detail:)](NavigationSplitView/init_columnVisibility_sidebar_content_detail.zh-Hans.md) for three columns.

The following code updates the first example above to always hide the first column when the view appears:

```swift
@State private var employeeIds: Set<Employee.ID> = []
@State private var columnVisibility =
    NavigationSplitViewVisibility.detailOnly

var body: some View {
    NavigationSplitView(columnVisibility: $columnVisibility) {
        List(model.employees, selection: $employeeIds) { employee in
            Text(employee.name)
        }
    } detail: {
        EmployeeDetails(for: employeeIds)
    }
}
```

The split view ignores the visibility control when it collapses its columns into a stack.

### Collapsed split views

At narrow size classes, such as on iPhone or Apple Watch, a navigation split view collapses into a single stack. Typically SwiftUI automatically chooses the view to show on top of this single stack, based on the content of the split view’s columns.

For custom navigation experiences, you can provide more information to help SwiftUI choose the right column. Create a `State` value of type [NavigationSplitViewColumn](NavigationSplitViewColumn.zh-Hans.md). Then pass a `Binding` to that state to the appropriate initializer, such as [init(preferredCompactColumn:sidebar:detail:)](NavigationSplitView/init_preferredCompactColumn_sidebar_detail.zh-Hans.md) or [init(preferredCompactColumn:sidebar:content:detail:)](NavigationSplitView/init_preferredCompactColumn_sidebar_content_detail.zh-Hans.md).

The following code shows the blue detail view when run on iPhone. When the person using the app taps the back button, they’ll see the yellow view. The value of `preferredPreferredCompactColumn` will change from `.detail` to `.sidebar`:

```swift
@State private var preferredColumn =
    NavigationSplitViewColumn.detail

var body: some View {
    NavigationSplitView(preferredCompactColumn: $preferredColumn) {
        Color.yellow
    } detail: {
        Color.blue
    }
}
```

### Customize a split view

To specify a preferred column width in a navigation split view, use the [navigationSplitViewColumnWidth(_:)](View/navigationSplitViewColumnWidth.zh-Hans.md) modifier. To set minimum, maximum, and ideal sizes for a column, use [navigationSplitViewColumnWidth(min:ideal:max:)](View/navigationSplitViewColumnWidth_min_ideal_max.zh-Hans.md). You can specify a different modifier in each column. The navigation split view does its best to accommodate the preferences that you specify, but might make adjustments based on other constraints.

To specify how columns in a navigation split view interact, use the [navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md) modifier with a [NavigationSplitViewStyle](NavigationSplitViewStyle.zh-Hans.md) value. For example, you can specify whether to emphasize the detail column or to give all of the columns equal prominence.

On some platforms, `NavigationSplitView` adds a [sidebarToggle](ToolbarDefaultItemKind/sidebarToggle.zh-Hans.md) toolbar item. Use the [toolbar(removing:)](View/toolbar_removing.zh-Hans.md) modifier to remove the default item.

## Creating a navigation split view

- **init(sidebar:detail:)**: Creates a two-column navigation split view.
- **init(sidebar:content:detail:)**: Creates a three-column navigation split view.

## Hiding columns in a navigation split view

- **init(columnVisibility:sidebar:detail:)**: Creates a two-column navigation split view that enables programmatic control of the sidebar’s visibility.
- **init(columnVisibility:sidebar:content:detail:)**: Creates a three-column navigation split view that enables programmatic control of leading columns’ visibility.

## Specifying a preferred compact column

- **init(preferredCompactColumn:sidebar:detail:)**: Creates a two-column navigation split view that enables programmatic control over which column appears on top when the view collapses into a single column in narrow sizes.
- **init(preferredCompactColumn:sidebar:content:detail:)**: Creates a three-column navigation split view that enables programmatic control over which column appears on top when the view collapses into a single column in narrow sizes.

## Specifying a preferred compact column and column visibility

- **init(columnVisibility:preferredCompactColumn:sidebar:detail:)**: Creates a two-column navigation split view that enables programmatic control of the sidebar’s visibility in regular sizes and which column appears on top when the view collapses into a single column in narrow sizes.
- **init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)**: Creates a three-column navigation split view that enables programmatic control of leading columns’ visibility in regular sizes and which column appears on top when the view collapses into a single column in narrow sizes.

## Presenting views in columns

- **Bringing robust navigation structure to your SwiftUI app**: Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.
- **Migrating to new navigation types**: Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.
- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationSplitViewVisibility**: The visibility of the leading columns in a navigation split view.
- **NavigationLink**: A view that controls a navigation presentation.

## Conforms To

- View

