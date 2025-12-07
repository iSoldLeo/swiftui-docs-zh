---
来源： https://developer.apple.com/documentation/SwiftUI/MenuStyle/button
抓取时间： 2025-12-03T06:09:40Z
---

# 按钮

**类型属性**

一种菜单样式，显示一个按钮，按下时可切换菜单内容的显示。

## 声明

```swift
@MainActor @preconcurrency static var button: ButtonMenuStyle { get }
```

## 讨论

在 macOS 上，该按钮会显示一个箭头，表示它显示了一个菜单。

按下后拖动到内容中，松开后即可激活所选操作。

## 获取内置菜单样式

- **automatic**：基于菜单上下文的默认菜单样式。
- **borderedButton**：显示边框按钮的菜单样式，按下时可切换菜单内容的显示。
- **borderlessButton**：显示无边框按钮的菜单样式，按下时可切换显示菜单内容。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuStyle/button
crawled: 2025-12-03T06:09:40Z
---

# button

**Type Property**

A menu style that displays a button that toggles the display of the menu’s contents when pressed.

## Declaration

```swift
@MainActor @preconcurrency static var button: ButtonMenuStyle { get }
```

## Discussion

On macOS, the button displays an arrow to indicate that it presents a menu.

Pressing and then dragging into the contents activates the selected action on release.

## Getting built-in menu styles

- **automatic**: The default menu style, based on the menu’s context.
- **borderedButton**: A menu style that displays a bordered button that toggles the display of the menu’s contents when pressed.
- **borderlessButton**: A menu style that displays a borderless button that toggles the display of the menu’s contents when pressed.

