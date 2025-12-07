---
来源： https://developer.apple.com/documentation/SwiftUI/MenuStyle
抓取时间： 2025-12-02T17:33:07Z
---

# 菜单样式

**Protocol**

将标准交互行为和自定义外观应用于视图层次结构中所有菜单的类型。

### 声明

```swift
@MainActor @preconcurrency protocol MenuStyle
```

## 概览

要为视图层次结构配置当前菜单样式，请使用 [menuStyle(_:)](View/menuStyle.zh-Hans.md) 修改器。

如果符合该协议的类型的基本声明中包含了该协议，则该类型将继承`@preconcurrency @MainActor` 隔离协议：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置菜单样式

- **automatic**：基于菜单上下文的默认菜单样式。
- **button**：一种菜单样式，显示一个按钮，按下时可切换菜单内容的显示。
- **borderedButton**：一种菜单样式，显示一个带边框的按钮，按下时可切换菜单内容的显示。
- **borderlessButton**：显示无边框按钮的菜单样式，按下时可切换菜单内容的显示。

## 创建自定义菜单样式

- **makeBody(configuration:)**：创建表示菜单主体的视图。
- **MenuStyle.Configuration**：菜单的属性。
- **Body**：表示菜单主体的视图。

## 支持类型

- **DefaultMenuStyle**：默认菜单样式，基于菜单的上下文。
- **ButtonMenuStyle**：一种菜单样式，显示一个按钮，按下时可切换菜单内容的显示。
- **BorderlessButtonMenuStyle**：显示无边框按钮的菜单样式，按下时可切换菜单内容的显示。
- **BorderedButtonMenuStyle**：显示有边框按钮的菜单样式，按下时可切换菜单内容的显示。

## 菜单样式

- **menuStyle(_:)**：为该视图中的菜单设置样式。
- **MenuStyleConfiguration**：菜单的配置。

## 符合类型

- 有边框按钮菜单样式（BorderedButtonMenuStyle
- 无边框按钮菜单样式
- 按钮菜单样式
- 默认菜单样式


---
source: https://developer.apple.com/documentation/SwiftUI/MenuStyle
crawled: 2025-12-02T17:33:07Z
---

# MenuStyle

**Protocol**

A type that applies standard interaction behavior and a custom appearance to all menus within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol MenuStyle
```

## Overview

To configure the current menu style for a view hierarchy, use the [menuStyle(_:)](View/menuStyle.zh-Hans.md) modifier.

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting built-in menu styles

- **automatic**: The default menu style, based on the menu’s context.
- **button**: A menu style that displays a button that toggles the display of the menu’s contents when pressed.
- **borderedButton**: A menu style that displays a bordered button that toggles the display of the menu’s contents when pressed.
- **borderlessButton**: A menu style that displays a borderless button that toggles the display of the menu’s contents when pressed.

## Creating custom menu styles

- **makeBody(configuration:)**: Creates a view that represents the body of a menu.
- **MenuStyle.Configuration**: The properties of a menu.
- **Body**: A view that represents the body of a menu.

## Supporting types

- **DefaultMenuStyle**: The default menu style, based on the menu’s context.
- **ButtonMenuStyle**: A menu style that displays a button that toggles the display of the menu’s contents when pressed.
- **BorderlessButtonMenuStyle**: A menu style that displays a borderless button that toggles the display of the menu’s contents when pressed.
- **BorderedButtonMenuStyle**: A menu style that displays a bordered button that toggles the display of the menu’s contents when pressed.

## Styling menus

- **menuStyle(_:)**: Sets the style for menus within this view.
- **MenuStyleConfiguration**: A configuration of a menu.

## Conforming Types

- BorderedButtonMenuStyle
- BorderlessButtonMenuStyle
- ButtonMenuStyle
- DefaultMenuStyle

