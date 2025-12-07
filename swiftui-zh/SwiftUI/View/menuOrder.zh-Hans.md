--- 来源：https://developer.apple.com/documentation/SwiftUI/View/menuOrder(_:)

抓取时间：2025-11-30T21:21:37Z

---

# menuOrder(_:)

**实例方法**

设置此视图中菜单项的首选顺序。

## 声明

```swift
nonisolated func menuOrder(_ order: MenuOrder) -> some View

```

## 参数

- **order**：要应用的菜单项排序策略。

## 返回值

使用指定菜单排序策略的视图。

## 说明

使用此修饰符可以覆盖默认菜单顺序。在支持的平台上，[priority](../MenuOrder/priority.zh-Hans.md) order 会将第一个菜单项保持在用户交互点附近，而 [fixed](../MenuOrder/fixed.zh-Hans.md) order 则始终从上到下排列菜单项。

在 iOS 系统中，对于位于可滚动内容中的菜单，[automatic](../MenuOrder/automatic.zh-Hans.md) 顺序会解析为 [fixed](../MenuOrder/fixed.zh-Hans.md)。使用 [menu](../PickerStyle/menu.zh-Hans.md) 样式的选择器也默认使用 [fixed](../MenuOrder/fixed.zh-Hans.md) 顺序。在所有其他情况下，菜单默认使用 [priority](../MenuOrder/priority.zh-Hans.md) 顺序。

在 macOS、tvOS 和 watchOS 系统中，[automatic](../MenuOrder/automatic.zh-Hans.md) 顺序始终解析为 [fixed](../MenuOrder/fixed.zh-Hans.md) 顺序。

以下示例创建了一个菜单，其内容按从上到下的固定顺序显示：

```swift
Menu {
    Button("Select", action: selectFolders)
    Button("New Folder", action: createFolder)
    Picker("Appearance", selection: $appearance) {
        Label("Icons", systemImage: "square.grid.2x2").tag(Appearance.icons)
        Label("List", systemImage: "list.bullet").tag(Appearance.list)
    }
} label: {
    Label("Settings", systemImage: "ellipsis.circle")
}
.menuOrder(.fixed)
```

您可以在显示菜单的控件上使用此修饰符。例如，以下代码使用 [menu](../PickerStyle/menu.zh-Hans.md) 样式，并按优先级顺序创建 [Picker](../Picker.zh-Hans.md)：

```swift
Picker("Flavor", selection: $selectedFlavor) {
    Text("Chocolate").tag(Flavor.chocolate)
    Text("Vanilla").tag(Flavor.vanilla)
    Text("Strawberry").tag(Flavor.strawberry)
}
.pickerStyle(.menu)
.menuOrder(.priority)
```

您也可以在上下文菜单中使用此修饰符。以下示例创建了一个上下文菜单，其内容按固定顺序显示：

```swift
Text("Favorite Card Suit")
    .padding()
    .contextMenu {
        Button("♥️ - Hearts", action: selectHearts)
        Button("♣️ - Clubs", action: selectClubs)
        Button("♠️ - Spades", action: selectSpades)
        Button("♦️ - Diamonds", action: selectDiamonds)
    }
    .menuOrder(.fixed)
```

此修饰符应用于菜单的子部分或子菜单时无效。

## 设置首选顺序

- **menuOrder**：从此视图显示的菜单项的首选顺序。

- **MenuOrder**：菜单显示其内容的顺序。


---
source: https://developer.apple.com/documentation/SwiftUI/View/menuOrder(_:)
crawled: 2025-11-30T21:21:37Z
---

# menuOrder(_:)

**Instance Method**

Sets the preferred order of items for menus presented from this view.

## Declaration

```swift
nonisolated func menuOrder(_ order: MenuOrder) -> some View

```

## Parameters

- **order**: The menu item ordering strategy to apply.

## Return Value

A view that uses the specified menu ordering strategy.

## Discussion

Use this modifier to override the default menu order. On supported platforms, [priority](../MenuOrder/priority.zh-Hans.md) order keeps the first items closer to the user’s point of interaction, whereas [fixed](../MenuOrder/fixed.zh-Hans.md) order always orders items from top to bottom.

On iOS, the [automatic](../MenuOrder/automatic.zh-Hans.md) order resolves to [fixed](../MenuOrder/fixed.zh-Hans.md) for menus presented within scrollable content. Pickers that use the [menu](../PickerStyle/menu.zh-Hans.md) style also default to [fixed](../MenuOrder/fixed.zh-Hans.md) order. In all other cases, menus default to [priority](../MenuOrder/priority.zh-Hans.md) order.

On macOS, tvOS and watchOS, the [automatic](../MenuOrder/automatic.zh-Hans.md) order always resolves to [fixed](../MenuOrder/fixed.zh-Hans.md) order.

The following example creates a menu that presents its content in a fixed order from top to bottom:

```swift
Menu {
    Button("Select", action: selectFolders)
    Button("New Folder", action: createFolder)
    Picker("Appearance", selection: $appearance) {
        Label("Icons", systemImage: "square.grid.2x2").tag(Appearance.icons)
        Label("List", systemImage: "list.bullet").tag(Appearance.list)
    }
} label: {
    Label("Settings", systemImage: "ellipsis.circle")
}
.menuOrder(.fixed)
```

You can use this modifier on controls that present a menu. For example, the code below creates a [Picker](../Picker.zh-Hans.md) using the [menu](../PickerStyle/menu.zh-Hans.md) style with a priority-based order:

```swift
Picker("Flavor", selection: $selectedFlavor) {
    Text("Chocolate").tag(Flavor.chocolate)
    Text("Vanilla").tag(Flavor.vanilla)
    Text("Strawberry").tag(Flavor.strawberry)
}
.pickerStyle(.menu)
.menuOrder(.priority)
```

You can also use this modifier on context menus. The example below creates a context menu that presents its content in a fixed order:

```swift
Text("Favorite Card Suit")
    .padding()
    .contextMenu {
        Button("♥️ - Hearts", action: selectHearts)
        Button("♣️ - Clubs", action: selectClubs)
        Button("♠️ - Spades", action: selectSpades)
        Button("♦️ - Diamonds", action: selectDiamonds)
    }
    .menuOrder(.fixed)
```

The modifier has no effect when applied to a subsection or submenu of a menu.

## Setting a preferred order

- **menuOrder**: The preferred order of items for menus presented from this view.
- **MenuOrder**: The order in which a menu presents its content.

