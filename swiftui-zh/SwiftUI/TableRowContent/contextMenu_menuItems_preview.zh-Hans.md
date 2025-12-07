--- 来源：https://developer.apple.com/documentation/SwiftUI/TableRowContent/contextMenu(menuItems:preview:)

抓取时间：2025-12-01T11:30:34Z

---

# contextMenu(menuItems:preview:)

**实例方法**

向表格行添加带有预览的上下文菜单。

## 声明

```swift
@MainActor @preconcurrency func contextMenu<M, P>(@ViewBuilder menuItems: () -> M, @ViewBuilder preview: () -> P) -> ModifiedContent<Self, _ContextMenuPreviewTableRowModifier<M, P>> where M : View, P : View
```

## 参数

- **menuItems**：一个用于生成菜单内容的闭包。您可以通过从闭包中返回空值来禁用上下文菜单。

- **preview**：系统与菜单一起显示的视图。

## 返回值

一个可以显示带有预览的上下文菜单的行。

## 讨论

使用此修饰符向表格中的行添加上下文菜单时，系统会在菜单旁边显示预览。您可以通过从闭包 `menuItems` 返回诸如 [Button](../Button.zh-Hans.md)、[Toggle](../Toggle.zh-Hans.md) 和 [Picker](../Picker.zh-Hans.md) 之类的控件来构建菜单。您还可以使用 [Menu](../Menu.zh-Hans.md) 来定义子菜单。

您可以通过从闭包 `preview` 返回视图来定义预览。系统会根据预览内容的大小调整其大小。例如，以下代码为表格中的每一行添加一个带有预览的上下文菜单，用户可以使用该菜单向该行所代表的人员发送电子邮件：

```swift
Table(of: Person.self) {
    TableColumn("Given Name", value: \.givenName)
    TableColumn("Family Name", value: \.familyName)
} rows: {
    ForEach(people) { person in
        TableRow(person)
            .contextMenu {
                Button("Send Email...") { }
            } preview: {
                Image("envelope") // Loads the image from an asset catalog.
            }
    }
}
```

如果您不需要预览，请使用 [contextMenu(menuItems:)](contextMenu_menuItems.zh-Hans.md)。如果要显示基于当前选择项的上下文菜单，请使用 [contextMenu(forSelectionType:menu:primaryAction:)](../View/contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md)。要向其他类型的视图添加上下文菜单，请参阅 [contextMenu(menuItems:)](../View/contextMenu_menuItems.zh-Hans.md)。

## 向行添加上下文菜单

- **contextMenu(menuItems:)**：向表格行添加上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowContent/contextMenu(menuItems:preview:)
crawled: 2025-12-01T11:30:34Z
---

# contextMenu(menuItems:preview:)

**Instance Method**

Adds a context menu with a preview to a table row.

## Declaration

```swift
@MainActor @preconcurrency func contextMenu<M, P>(@ViewBuilder menuItems: () -> M, @ViewBuilder preview: () -> P) -> ModifiedContent<Self, _ContextMenuPreviewTableRowModifier<M, P>> where M : View, P : View
```

## Parameters

- **menuItems**: A closure that produces the menu’s contents. You can deactivate the context menu by returning nothing from the closure.
- **preview**: A view that the system displays along with the menu.

## Return Value

A row that can display a context menu with a preview.

## Discussion

When you use this modifier to add a context menu to rows in a table, the system shows a preview beside the menu. Compose the menu by returning controls like [Button](../Button.zh-Hans.md), [Toggle](../Toggle.zh-Hans.md), and [Picker](../Picker.zh-Hans.md) from the `menuItems` closure. You can also use [Menu](../Menu.zh-Hans.md) to define submenus.

Define the preview by returning a view from the `preview` closure. The system sizes the preview to match the size of its content. For example, the following code adds a context menu with a preview to each row in a table that people can use to send an email to the person represented by that row:

```swift
Table(of: Person.self) {
    TableColumn("Given Name", value: \.givenName)
    TableColumn("Family Name", value: \.familyName)
} rows: {
    ForEach(people) { person in
        TableRow(person)
            .contextMenu {
                Button("Send Email...") { }
            } preview: {
                Image("envelope") // Loads the image from an asset catalog.
            }
    }
}
```



If you don’t need a preview, use [contextMenu(menuItems:)](contextMenu_menuItems.zh-Hans.md). If you want to display a context menu that’s based on the current selection, use [contextMenu(forSelectionType:menu:primaryAction:)](../View/contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md). To add context menus to other kinds of views, see [contextMenu(menuItems:)](../View/contextMenu_menuItems.zh-Hans.md).

## Adding a context menu to a row

- **contextMenu(menuItems:)**: Adds a context menu to a table row.

