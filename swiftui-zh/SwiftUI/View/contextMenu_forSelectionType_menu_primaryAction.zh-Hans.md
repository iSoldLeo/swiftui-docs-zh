--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contextMenu(forSelectionType:menu:primaryAction:)

抓取时间：2025-12-02T17:36:16Z

---

# contextMenu(forSelectionType:menu:primaryAction:)

**实例方法**

向视图添加基于项的上下文菜单。

## 声明

```swift
nonisolated func contextMenu<I, M>(forSelectionType itemType: I.Type = I.self, @ViewBuilder menu: @escaping (Set<I>) -> M, primaryAction: ((Set<I>) -> Void)? = nil) -> some View where I : Hashable, M : View

```

## 参数

- **itemType**：项的标识符类型。确保其与容器的选择类型匹配。

- **menu**：生成菜单的闭包。闭包的单个参数包含要操作的项集。空集表示对可选容器的空白区域激活菜单，而非空集表示对已选项激活菜单。使用诸如 [Button](../Button.zh-Hans.md)、[Picker](../Picker.zh-Hans.md) 和 [Toggle](../Toggle.zh-Hans.md) 之类的控件来定义菜单项。您还可以使用 [Menu](../Menu.zh-Hans.md) 创建子菜单，或使用 [Section](../Section.zh-Hans.md) 对菜单项进行分组。您可以通过从闭包中不返回任何值来禁用上下文菜单。

- **primaryAction**：一个闭包，用于定义响应主要交互而要执行的操作。闭包的单个参数包含要操作的菜单项集合。

## 返回值

一个可以显示基于菜单项的上下文菜单的视图。

## 说明

您可以将基于菜单项的上下文菜单添加到支持选择的容器中，例如 [List](../List.zh-Hans.md) 或 [Table](../Table.zh-Hans.md)。在用于定义菜单的闭包中，您会收到一个项目集合，该集合取决于容器的选择状态以及用户点击或轻触以激活菜单的位置。该集合包含：

- 当用户从任何已选项目启动上下文菜单时，该集合包含已选项目。

- 如果用户从容器的空白区域点击或轻触以激活上下文菜单，则该集合不包含任何内容。即使当前已选中一个或多个项目，情况也是如此。

您可以根据已选项目的数量来更改菜单内容。例如，以下代码包含一个列表，其中定义了空白区域菜单、单项菜单和多项菜单：

```swift
struct ContextMenuItemExample: View {
    var items: [Item]
    @State private var selection = Set<Item.ID>()

    var body: some View {
        List(selection: $selection) {
            ForEach(items) { item in
                Text(item.name)
            }
        }
        .contextMenu(forSelectionType: Item.ID.self) { items in
            if items.isEmpty { // Empty area menu.
                Button("New Item") { }

            } else if items.count == 1 { // Single item menu.
                Button("Copy") { }
                Button("Delete", role: .destructive) { }

            } else { // Multi-item menu.
                Button("Copy") { }
                Button("New Folder With Selection") { }
                Button("Delete Selected", role: .destructive) { }
            }
        }
    }
}
```

以上示例假设 `Item` 类型符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议，并且依赖于关联的 `ID` 类型来呈现选择和上下文菜单。

如果将修饰符添加到视图层级结构中，而该层级结构中没有支持选择的容器，则上下文菜单永远不会激活。要添加不依赖于选择行为的上下文菜单，请使用 [contextMenu(menuItems:)](contextMenu_menuItems.zh-Hans.md)。要将上下文菜单添加到表格中的特定行，请使用 [contextMenu(menuItems:)](../TableRowContent/contextMenu_menuItems.zh-Hans.md)。

### 添加主要操作

您可以选择向上下文菜单添加自定义主要操作。在 macOS 中，单击可选容器中的行即可选中该行，双击则执行主要操作。在 iOS 和 iPadOS 中，轻点行即可激活主要操作。要选择行而不执行任何操作，请进入编辑模式，或在轻点行时按住键盘上的 Shift 或 Command 键。

例如，您可以修改上例中的上下文菜单，以便在 macOS 上双击行时打开一个新窗口来显示所选项目。从环境中获取 [OpenWindowAction](../OpenWindowAction.zh-Hans.md)：

```swift
@Environment(\.openWindow) private var openWindow
```

然后，在 `primaryAction` 闭包中，对每个项目调用 [openWindow](../EnvironmentValues/openWindow.zh-Hans.md)：

```swift
.contextMenu(forSelectionType: Item.ID.self) { items in
    // ...
} primaryAction: { items in
    for item in items {
        openWindow(value: item)
    }
}
```

打开窗口的操作取决于 [App](../App.zh-Hans.md) 中对 `Item` 类型响应的 [WindowGroup](../WindowGroup.zh-Hans.md) 场景的声明：

```swift
WindowGroup("Item Detail", for: Item.self) { $item in
    // ...
}
```

## 创建上下文菜单

- **contextMenu(menuItems:)**：向视图添加上下文菜单。

- **contextMenu(menuItems:preview:)**：向视图添加带有自定义预览的上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contextMenu(forSelectionType:menu:primaryAction:)
crawled: 2025-12-02T17:36:16Z
---

# contextMenu(forSelectionType:menu:primaryAction:)

**Instance Method**

Adds an item-based context menu to a view.

## Declaration

```swift
nonisolated func contextMenu<I, M>(forSelectionType itemType: I.Type = I.self, @ViewBuilder menu: @escaping (Set<I>) -> M, primaryAction: ((Set<I>) -> Void)? = nil) -> some View where I : Hashable, M : View

```

## Parameters

- **itemType**: The identifier type of the items. Ensure that this matches the container’s selection type.
- **menu**: A closure that produces the menu. A single parameter to the closure contains the set of items to act on. An empty set indicates menu activation over the empty area of the selectable container, while a non-empty set indicates menu activation over selected items. Use controls like [Button](../Button.zh-Hans.md), [Picker](../Picker.zh-Hans.md), and [Toggle](../Toggle.zh-Hans.md) to define the menu items. You can also create submenus using [Menu](../Menu.zh-Hans.md), or group items with [Section](../Section.zh-Hans.md). You can deactivate the context menu by returning nothing from the closure.
- **primaryAction**: A closure that defines the action to perform in response to the primary interaction. A single parameter to the closure contains the set of items to act on.

## Return Value

A view that can display an item-based context menu.

## Discussion

You can add an item-based context menu to a container that supports selection, like a [List](../List.zh-Hans.md) or a [Table](../Table.zh-Hans.md). In the closure that you use to define the menu, you receive a collection of items that depends on the selection state of the container and the location where the person clicks or taps to activate the menu. The collection contains:

- The selected item or items, when people initiate the context menu from any selected item.
- Nothing, if people tap or click to activate the context menu from an empty part of the container. This is true even when one or more items is currently selected.

You can vary the menu contents according to the number of selected items. For example, the following code has a list that defines an empty area menu, a single item menu, and a multi-item menu:

```swift
struct ContextMenuItemExample: View {
    var items: [Item]
    @State private var selection = Set<Item.ID>()

    var body: some View {
        List(selection: $selection) {
            ForEach(items) { item in
                Text(item.name)
            }
        }
        .contextMenu(forSelectionType: Item.ID.self) { items in
            if items.isEmpty { // Empty area menu.
                Button("New Item") { }

            } else if items.count == 1 { // Single item menu.
                Button("Copy") { }
                Button("Delete", role: .destructive) { }

            } else { // Multi-item menu.
                Button("Copy") { }
                Button("New Folder With Selection") { }
                Button("Delete Selected", role: .destructive) { }
            }
        }
    }
}
```

The above example assumes that the `Item` type conforms to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol, and relies on the associated `ID` type for both selection and context menu presentation.

If you add the modifier to a view hierarchy that doesn’t have a container that supports selection, the context menu never activates. To add a context menu that doesn’t depend on selection behavior, use [contextMenu(menuItems:)](contextMenu_menuItems.zh-Hans.md). To add a context menu to a specific row in a table, use [contextMenu(menuItems:)](../TableRowContent/contextMenu_menuItems.zh-Hans.md).

### Add a primary action

Optionally, you can add a custom primary action to the context menu. In macOS, a single click on a row in a selectable container selects that row, and a double click performs the primary action. In iOS and iPadOS, tapping on the row activates the primary action. To select a row without performing an action, either enter edit mode or hold shift or command on a keyboard while tapping the row.

For example, you can modify the context menu from the previous example so that double clicking the row on macOS opens a new window for selected items. Get the [OpenWindowAction](../OpenWindowAction.zh-Hans.md) from the environment:

```swift
@Environment(\.openWindow) private var openWindow
```

Then call [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) from inside the `primaryAction` closure for each item:

```swift
.contextMenu(forSelectionType: Item.ID.self) { items in
    // ...
} primaryAction: { items in
    for item in items {
        openWindow(value: item)
    }
}
```

The open window action depends on the declaration of a [WindowGroup](../WindowGroup.zh-Hans.md) scene in your [App](../App.zh-Hans.md) that responds to the `Item` type:

```swift
WindowGroup("Item Detail", for: Item.self) { $item in
    // ...
}
```

## Creating context menus

- **contextMenu(menuItems:)**: Adds a context menu to a view.
- **contextMenu(menuItems:preview:)**: Adds a context menu with a custom preview to a view.

