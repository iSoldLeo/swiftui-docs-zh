--- 来源：https://developer.apple.com/documentation/SwiftUI/TableRowContent/contextMenu(menuItems:)

抓取时间：2025-12-03T06:41:15Z

---

# contextMenu(menuItems:)

**实例方法**

向表格行添加上下文菜单。

## 声明

```swift
@MainActor @preconcurrency func contextMenu<M>(@ViewBuilder menuItems: () -> M) -> ModifiedContent<Self, _ContextMenuTableRowModifier<M>> where M : View
```

## 参数

- **menuItems**：一个用于生成菜单内容的闭包。您可以通过从闭包中返回空值来禁用上下文菜单。

## 返回值

一个可以显示上下文菜单的行。

## 说明

使用此修饰符向表格行添加上下文菜单。通过从闭包 `menuItems` 返回诸如 [Button](../Button.zh-Hans.md)、[Toggle](../Toggle.zh-Hans.md) 和 [Picker](../Picker.zh-Hans.md) 之类的控件来构建菜单。您还可以使用 [Menu](../Menu.zh-Hans.md) 定义子菜单，或使用 [Section](../Section.zh-Hans.md) 对项目进行分组。

以下示例为表格中的每一行添加一个上下文菜单，用户可以使用该菜单向该行所代表的人员发送电子邮件：

```swift
Table(of: Person.self) {
    TableColumn("Given Name", value: \.givenName)
    TableColumn("Family Name", value: \.familyName)
} rows: {
    ForEach(people) { person in
        TableRow(person)
            .contextMenu {
                Button("Send Email...") { }
            }
    }
}
```

如果要在上下文菜单旁边显示预览，请使用 [contextMenu(menuItems:preview:)](contextMenu_menuItems_preview.zh-Hans.md)。如果要显示基于当前选择的上下文菜单，请使用 [contextMenu(forSelectionType:menu:primaryAction:)](../View/contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md)。要向其他类型的视图添加上下文菜单，请使用 [contextMenu(menuItems:)](../View/contextMenu_menuItems.zh-Hans.md)。

## 向表格行添加上下文菜单

- **contextMenu(menuItems:preview:)**：向表格行添加带有预览的上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowContent/contextMenu(menuItems:)
crawled: 2025-12-03T06:41:15Z
---

# contextMenu(menuItems:)

**Instance Method**

Adds a context menu to a table row.

## Declaration

```swift
@MainActor @preconcurrency func contextMenu<M>(@ViewBuilder menuItems: () -> M) -> ModifiedContent<Self, _ContextMenuTableRowModifier<M>> where M : View
```

## Parameters

- **menuItems**: A closure that produces the menu’s contents. You can deactivate the context menu by returning nothing from the closure.

## Return Value

A row that can display a context menu.

## Discussion

Use this modifier to add a context menu to a table row. Compose the menu by returning controls like [Button](../Button.zh-Hans.md), [Toggle](../Toggle.zh-Hans.md), and [Picker](../Picker.zh-Hans.md) from the `menuItems` closure. You can also use [Menu](../Menu.zh-Hans.md) to define submenus, or [Section](../Section.zh-Hans.md) to group items.

The following example adds a context menu to each row in a table that people can use to send an email to the person represented by that row:

```swift
Table(of: Person.self) {
    TableColumn("Given Name", value: \.givenName)
    TableColumn("Family Name", value: \.familyName)
} rows: {
    ForEach(people) { person in
        TableRow(person)
            .contextMenu {
                Button("Send Email...") { }
            }
    }
}
```

If you want to display a preview beside the context menu, use [contextMenu(menuItems:preview:)](contextMenu_menuItems_preview.zh-Hans.md). If you want to display a context menu that’s based on the current selection, use [contextMenu(forSelectionType:menu:primaryAction:)](../View/contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md). To add context menus to other kinds of views, use [contextMenu(menuItems:)](../View/contextMenu_menuItems.zh-Hans.md).

## Adding a context menu to a row

- **contextMenu(menuItems:preview:)**: Adds a context menu with a preview to a table row.

