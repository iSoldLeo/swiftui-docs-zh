--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contextMenu(menuItems:preview:)

抓取时间：2025-11-30T21:21:22Z

---

# contextMenu(menuItems:preview:)

**实例方法**

向视图添加带有自定义预览的上下文菜单。

## 声明

```swift
nonisolated func contextMenu<M, P>(@ViewBuilder menuItems: () -> M, @ViewBuilder preview: () -> P) -> some View where M : View, P : View

```

## 参数

- **menuItems**：一个用于生成菜单内容的闭包。您可以通过从闭包中返回空值来禁用上下文菜单。

- **preview**：一个系统与菜单一起显示的视图。

## 返回值

一个可以显示带有预览的上下文菜单的视图。

## 讨论

当您使用此修饰符向应用程序用户界面中的视图添加上下文菜单时，系统会在菜单旁边显示自定义预览。您可以通过从 `menuItems` 闭包返回诸如 [Button](../Button.zh-Hans.md)、[Toggle](../Toggle.zh-Hans.md) 和 [Picker](../Picker.zh-Hans.md) 之类的控件来构建菜单。您还可以使用 [Menu](../Menu.zh-Hans.md) 定义子菜单，或使用 [Section](../Section.zh-Hans.md) 对菜单项进行分组。

您可以通过从 `preview` 闭包返回视图来定义自定义预览。系统会根据预览内容的大小自动调整其大小。例如，您可以向 [Text](../Text.zh-Hans.md) 视图添加一个双按钮上下文菜单，并使用 [Image](../Image.zh-Hans.md) 作为预览：

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
    } preview: {
        Image("turtlerock") // Loads the image from an asset catalog.
    }
```

当用户在 iOS 或 iPadOS 中使用长按等操作激活上下文菜单时，系统会显示图像和菜单：

要自定义在系统过渡到显示自定义 `preview` 时显示的升降预览，请应用类型为 [contextMenuPreview](../ContentShapeKinds/contextMenuPreview.zh-Hans.md) 的 [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md)。例如，您可以更改升降预览的圆角半径，或使用嵌套视图作为升降预览。

如果您不需要预览，请改用 [contextMenu(menuItems:)](contextMenu_menuItems.zh-Hans.md)。如果您想向支持选择功能的容器（例如 [List](../List.zh-Hans.md) 或 [Table](../Table.zh-Hans.md)）添加上下文菜单，并且希望区分选中项时的菜单激活和容器空白区域的菜单激活，请使用 [contextMenu(forSelectionType:menu:primaryAction:)](contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md)。

## 创建上下文菜单

- **contextMenu(menuItems:)**：向视图添加上下文菜单。

- **contextMenu(forSelectionType:menu:primaryAction:)**：向视图添加基于项目的上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contextMenu(menuItems:preview:)
crawled: 2025-11-30T21:21:22Z
---

# contextMenu(menuItems:preview:)

**Instance Method**

Adds a context menu with a custom preview to a view.

## Declaration

```swift
nonisolated func contextMenu<M, P>(@ViewBuilder menuItems: () -> M, @ViewBuilder preview: () -> P) -> some View where M : View, P : View

```

## Parameters

- **menuItems**: A closure that produces the menu’s contents. You can deactivate the context menu by returning nothing from the closure.
- **preview**: A view that the system displays along with the menu.

## Return Value

A view that can display a context menu with a preview.

## Discussion

When you use this modifer to add a context menu to a view in your app’s user interface, the system displays the custom preview beside the menu. Compose the menu by returning controls like [Button](../Button.zh-Hans.md), [Toggle](../Toggle.zh-Hans.md), and [Picker](../Picker.zh-Hans.md) from the `menuItems` closure. You can also use [Menu](../Menu.zh-Hans.md) to define submenus or [Section](../Section.zh-Hans.md) to group items.

Define the custom preview by returning a view from the `preview` closure. The system sizes the preview to match the size of its content. For example, you can add a two button context menu to a [Text](../Text.zh-Hans.md) view, and use an [Image](../Image.zh-Hans.md) as the preview:

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
    } preview: {
        Image("turtlerock") // Loads the image from an asset catalog.
    }
```

When someone activates the context menu with an action like touch and hold in iOS or iPadOS, the system displays the image and the menu:



To customize the lift preview, shown while the system transitions to show your custom `preview`, apply a [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) with a [contextMenuPreview](../ContentShapeKinds/contextMenuPreview.zh-Hans.md) kind. For example, you can change the lift preview’s corner radius or use a nested view as the lift preview.



If you don’t need a preview, use [contextMenu(menuItems:)](contextMenu_menuItems.zh-Hans.md) instead. If you want to add a context menu to a container that supports selection, like a [List](../List.zh-Hans.md) or a [Table](../Table.zh-Hans.md), and you want to distinguish between menu activation on a selection and activation in an empty area of the container, use [contextMenu(forSelectionType:menu:primaryAction:)](contextMenu_forSelectionType_menu_primaryAction.zh-Hans.md).

## Creating context menus

- **contextMenu(menuItems:)**: Adds a context menu to a view.
- **contextMenu(forSelectionType:menu:primaryAction:)**: Adds an item-based context menu to a view.

