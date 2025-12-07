---
来源： https://developer.apple.com/documentation/SwiftUI/MenuStyle/automatic
抓取时间： 2025-12-03T06:09:39Z
---

# 自动

**类型属性**

基于菜单上下文的默认菜单样式。

## 声明

```swift
@MainActor @preconcurrency static var automatic: DefaultMenuStyle { get }
```

## 讨论

默认菜单样式会因平台而异。默认情况下，macOS 使用边框按钮样式。

如果在容器内创建菜单，其样式将解析为该特定平台推荐的容器内菜单样式。例如，嵌套在另一个菜单中的菜单将解析为子菜单：

```swift
Menu("Edit") {
    Menu("Arrange") {
        Button("Bring to Front", action: moveSelectionToFront)
        Button("Send to Back", action: moveSelectionToBack)
    }
    Button("Delete", action: deleteSelection)
}
```

您可以覆盖菜单的样式。要将默认样式应用于菜单或包含菜单的视图，请使用[menuStyle(_:)](../View/menuStyle.zh-Hans.md)修饰符。

## 获取内置菜单样式

- **button**：一个菜单样式，显示一个按钮，按下时可切换菜单内容的显示。
- **borderedButton**：一种菜单样式，显示一个带边框的按钮，按下时可切换菜单内容的显示。
- **borderlessButton**：显示无边框按钮的菜单样式，按下时可切换显示菜单内容。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuStyle/automatic
crawled: 2025-12-03T06:09:39Z
---

# automatic

**Type Property**

The default menu style, based on the menu’s context.

## Declaration

```swift
@MainActor @preconcurrency static var automatic: DefaultMenuStyle { get }
```

## Discussion

The default menu style can vary by platform. By default, macOS uses the bordered button style.

If you create a menu inside a container, the style resolves to the recommended style for menus inside that container for that specific platform. For example, a menu nested within another menu will resolve to a submenu:

```swift
Menu("Edit") {
    Menu("Arrange") {
        Button("Bring to Front", action: moveSelectionToFront)
        Button("Send to Back", action: moveSelectionToBack)
    }
    Button("Delete", action: deleteSelection)
}
```

You can override a menu’s style. To apply the default style to a menu, or to a view that contains a menu, use the [menuStyle(_:)](../View/menuStyle.zh-Hans.md) modifier.

## Getting built-in menu styles

- **button**: A menu style that displays a button that toggles the display of the menu’s contents when pressed.
- **borderedButton**: A menu style that displays a bordered button that toggles the display of the menu’s contents when pressed.
- **borderlessButton**: A menu style that displays a borderless button that toggles the display of the menu’s contents when pressed.

