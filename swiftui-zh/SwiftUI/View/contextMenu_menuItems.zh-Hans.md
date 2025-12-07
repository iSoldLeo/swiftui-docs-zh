--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contextMenu(menuItems:)

抓取时间：2025-11-30T21:21:21Z

---

# contextMenu(menuItems:)

**实例方法**

向视图添加上下文菜单。

## 声明

```swift
nonisolated func contextMenu<MenuItems>(@ViewBuilder menuItems: () -> MenuItems) -> some View where MenuItems : View

```

## 参数

- **menuItems**：一个用于生成菜单内容的闭包。您可以通过从闭包中返回空值来禁用上下文菜单。

## 返回值

一个可以显示上下文菜单的视图。

## 说明

使用此修饰符向应用程序用户界面中的视图添加上下文菜单。通过从闭包 `menuItems` 返回控件（例如 [Button](../Button.zh-Hans.md)、[Toggle](../Toggle.zh-Hans.md) 和 [Picker](../Picker.zh-Hans.md)）来构建菜单。您还可以使用 [Menu](../Menu.zh-Hans.md) 定义子菜单，或使用 [Section](../Section.zh-Hans.md) 对项目进行分组。

以下示例创建了一个 [Text](../Text.zh-Hans.md) 视图，其中包含一个带有两个按钮的上下文菜单：

```swift
Text("Turtle Rock")
    .padding()
    .contextMenu {
        Button {
            // Add this item to a list of favorites.
        } label: {
            Label("Add to Favorites", systemImage: "heart")
        }
        Button {
            // Open Maps and center it on this item.
        } label: {
            Label("Show in Maps", systemImage: "mappin")
        }
    }
```

当用户在 iOS 或 iPadOS 中使用长按等操作激活上下文菜单时，系统会在内容旁边显示该菜单：

如果用户进行了选择，或者点击菜单外部区域，系统将关闭该菜单。

要自定义默认预览，请应用类型为 [contextMenuPreview](../ContentShapeKinds/contextMenuPreview.zh-Hans.md) 的 [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md)。例如，您可以更改预览的圆角半径或使用嵌套视图作为预览。

如果要显示不同的预览，可以使用 [contextMenu(menuItems:preview:)](contextMenu_menuItems_preview.zh-Hans.md)。要向支持选择的容器（例如 [List](../List.zh-Hans.md) 或 [Table](../Table.zh-Hans.md)）添加上下文菜单，并区分在选中项时激活菜单和在容器空白区域激活菜单，请使用 [contextMenu(forSelectionType:menu:primaryAction:)](contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md)。

## 创建上下文菜单

- **contextMenu(menuItems:preview:)**：向视图添加带有自定义预览的上下文菜单。

- **contextMenu(forSelectionType:menu:primaryAction:)**：向视图添加基于项目的上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contextMenu(menuItems:)
crawled: 2025-11-30T21:21:21Z
---

# contextMenu(menuItems:)

**Instance Method**

Adds a context menu to a view.

## Declaration

```swift
nonisolated func contextMenu<MenuItems>(@ViewBuilder menuItems: () -> MenuItems) -> some View where MenuItems : View

```

## Parameters

- **menuItems**: A closure that produces the menu’s contents. You can deactivate the context menu by returning nothing from the closure.

## Return Value

A view that can display a context menu.

## Discussion

Use this modifier to add a context menu to a view in your app’s user interface. Compose the menu by returning controls like [Button](../Button.zh-Hans.md), [Toggle](../Toggle.zh-Hans.md), and [Picker](../Picker.zh-Hans.md) from the `menuItems` closure. You can also use [Menu](../Menu.zh-Hans.md) to define submenus or [Section](../Section.zh-Hans.md) to group items.

The following example creates a [Text](../Text.zh-Hans.md) view that has a context menu with two buttons:

```swift
Text("Turtle Rock")
    .padding()
    .contextMenu {
        Button {
            // Add this item to a list of favorites.
        } label: {
            Label("Add to Favorites", systemImage: "heart")
        }
        Button {
            // Open Maps and center it on this item.
        } label: {
            Label("Show in Maps", systemImage: "mappin")
        }
    }
```

When someone activates the context menu with an action like touch and hold in iOS or iPadOS, the system displays the menu next to the content:



The system dismisses the menu if someone makes a selection, or taps or clicks outside the menu.

To customize the default preview, apply a [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) with a [contextMenuPreview](../ContentShapeKinds/contextMenuPreview.zh-Hans.md) kind. For example, you can change the preview’s corner radius or use a nested view as the preview.



If you want to show a different preview, you can use [contextMenu(menuItems:preview:)](contextMenu_menuItems_preview.zh-Hans.md). To add a context menu to a container that supports selection, like a [List](../List.zh-Hans.md) or a [Table](../Table.zh-Hans.md), and to distinguish between menu activation on a selection and activation in an empty area of the container, use [contextMenu(forSelectionType:menu:primaryAction:)](contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md).

## Creating context menus

- **contextMenu(menuItems:preview:)**: Adds a context menu with a custom preview to a view.
- **contextMenu(forSelectionType:menu:primaryAction:)**: Adds an item-based context menu to a view.

