---
来源： https://developer.apple.com/documentation/SwiftUI/MenuStyle/borderedButton
抓取时间： 2025-12-03T06:09:40Z
---

# 边框按钮

**类型属性**

一种菜单样式，显示一个边框按钮，按下时可切换菜单内容的显示。

### 声明

```swift
@MainActor @preconcurrency static var borderedButton: BorderedButtonMenuStyle { get }
```

## 讨论

在 macOS 上，按钮会显示一个箭头，表示它显示了一个菜单。

按下后拖动到内容中，松开后即可触发所选操作。

## 获取内置菜单样式

- **automatic**：基于菜单上下文的默认菜单样式。
- **button**：显示按钮的菜单样式，按下按钮时可切换菜单内容的显示。
- **borderlessButton**：显示无边框按钮的菜单样式，按下时可切换菜单内容的显示。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuStyle/borderedButton
crawled: 2025-12-03T06:09:40Z
---

# borderedButton

**Type Property**

A menu style that displays a bordered button that toggles the display of the menu’s contents when pressed.

## Declaration

```swift
@MainActor @preconcurrency static var borderedButton: BorderedButtonMenuStyle { get }
```

## Discussion

On macOS, the button displays an arrow indicating that it presents a menu.

Pressing and then dragging into the contents triggers the chosen action on release.

## Getting built-in menu styles

- **automatic**: The default menu style, based on the menu’s context.
- **button**: A menu style that displays a button that toggles the display of the menu’s contents when pressed.
- **borderlessButton**: A menu style that displays a borderless button that toggles the display of the menu’s contents when pressed.

