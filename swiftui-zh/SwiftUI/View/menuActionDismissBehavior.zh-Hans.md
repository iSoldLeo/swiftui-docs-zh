--- 来源：https://developer.apple.com/documentation/SwiftUI/View/menuActionDismissBehavior(_:)

抓取时间：2025-12-02T17:36:31Z

---

# menuActionDismissBehavior(_:)

**实例方法**

告诉菜单在执行操作后是否关闭。

## 声明

```swift
nonisolated func menuActionDismissBehavior(_ behavior: MenuActionDismissBehavior) -> some View

```

## 返回值

返回一个具有指定菜单关闭行为的视图。

## 说明

使用此修饰符来控制菜单的关闭行为。在以下示例中，用户选择“增加”或“减少”操作后，菜单不会自动关闭：

```swift
Menu("Font size") {
    Button(action: increase) {
        Label("Increase", systemImage: "plus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)

    Button("Reset", action: reset)

    Button(action: decrease) {
        Label("Decrease", systemImage: "minus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)
}
```

您可以在任何显示菜单的控件上使用此修饰符，例如使用 [menu](../PickerStyle/menu.zh-Hans.md) 样式的 [Picker](../Picker.zh-Hans.md) 或 [ControlGroup](../ControlGroup.zh-Hans.md)。例如，以下代码创建了一个选择器，当用户选择其中一个选项时，菜单不会自动关闭：

```swift
Picker("Flavor", selection: $selectedFlavor) {
    ForEach(Flavor.allCases) { flavor in
        Text(flavor.rawValue.capitalized)
            .tag(flavor)
    }
}
.pickerStyle(.menu)
.menuActionDismissBehavior(.disabled)
```

您也可以在上下文菜单中使用此修饰符。以下示例创建了一个上下文菜单，在用户选择要执行的操作后，菜单仍然保持显示状态：

```swift
Text("Favorite Card Suit")
    .padding()
    .contextMenu {
        Button("♥️ - Hearts", action: increaseHeartsCount)
        Button("♣️ - Clubs", action: increaseClubsCount)
        Button("♠️ - Spades", action: increaseSpadesCount)
        Button("♦️ - Diamonds", action: increaseDiamondsCount)
    }
    .menuActionDismissBehavior(.disabled)
```

## 配置菜单关闭

- **MenuActionDismissBehavior**：菜单关闭行为选项集。


---
source: https://developer.apple.com/documentation/SwiftUI/View/menuActionDismissBehavior(_:)
crawled: 2025-12-02T17:36:31Z
---

# menuActionDismissBehavior(_:)

**Instance Method**

Tells a menu whether to dismiss after performing an action.

## Declaration

```swift
nonisolated func menuActionDismissBehavior(_ behavior: MenuActionDismissBehavior) -> some View

```

## Return Value

A view that has the specified menu dismissal behavior.

## Discussion

Use this modifier to control the dismissal behavior of a menu. In the example below, the menu doesn’t dismiss after someone chooses either the increase or decrease action:

```swift
Menu("Font size") {
    Button(action: increase) {
        Label("Increase", systemImage: "plus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)

    Button("Reset", action: reset)

    Button(action: decrease) {
        Label("Decrease", systemImage: "minus.magnifyingglass")
    }
    .menuActionDismissBehavior(.disabled)
}
```

You can use this modifier on any controls that present a menu, like a [Picker](../Picker.zh-Hans.md) that uses the [menu](../PickerStyle/menu.zh-Hans.md) style or a [ControlGroup](../ControlGroup.zh-Hans.md). For example, the code below creates a picker that disables dismissal when someone selects one of the options:

```swift
Picker("Flavor", selection: $selectedFlavor) {
    ForEach(Flavor.allCases) { flavor in
        Text(flavor.rawValue.capitalized)
            .tag(flavor)
    }
}
.pickerStyle(.menu)
.menuActionDismissBehavior(.disabled)
```

You can also use this modifier on context menus. The example below creates a context menu that stays presented after someone selects an action to run:

```swift
Text("Favorite Card Suit")
    .padding()
    .contextMenu {
        Button("♥️ - Hearts", action: increaseHeartsCount)
        Button("♣️ - Clubs", action: increaseClubsCount)
        Button("♠️ - Spades", action: increaseSpadesCount)
        Button("♦️ - Diamonds", action: increaseDiamondsCount)
    }
    .menuActionDismissBehavior(.disabled)
```

## Configuring menu dismissal

- **MenuActionDismissBehavior**: The set of menu dismissal behavior options.

