---
来源： https://developer.apple.com/documentation/SwiftUI/MenuStyleConfiguration
抓取时间： 2025-12-02T17:33:08Z
---

# MenuStyleConfiguration

**Structure**

菜单的配置。

## 声明

```swift
struct MenuStyleConfiguration
```

## 概览

使用 [init(_:)](Menu/init.zh-Hans.md) 的 [Menu](Menu.zh-Hans.md) 初始化器使用当前菜单样式创建一个实例，您可以修改该实例以创建自定义样式。

例如，下面的代码创建了一个新的自定义样式，为当前菜单样式添加了红色边框：

```swift
struct RedBorderMenuStyle: MenuStyle {
    func makeBody(configuration: Configuration) -> some View {
        Menu(configuration)
            .border(Color.red)
    }
}
```

## 设置标签和内容

- **MenuStyleConfiguration.Label**：菜单的类型化标签。
- **MenuStyleConfiguration.Content**：菜单中经过类型化的内容。

## 菜单样式

- **menuStyle(_:)**：为该视图中的菜单设置样式。
- **MenuStyle**：对视图层次结构中的所有菜单应用标准交互行为和自定义外观的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/MenuStyleConfiguration
crawled: 2025-12-02T17:33:08Z
---

# MenuStyleConfiguration

**Structure**

A configuration of a menu.

## Declaration

```swift
struct MenuStyleConfiguration
```

## Overview

Use the [init(_:)](Menu/init.zh-Hans.md) initializer of [Menu](Menu.zh-Hans.md) to create an instance using the current menu style, which you can modify to create a custom style.

For example, the following code creates a new, custom style that adds a red border to the current menu style:

```swift
struct RedBorderMenuStyle: MenuStyle {
    func makeBody(configuration: Configuration) -> some View {
        Menu(configuration)
            .border(Color.red)
    }
}
```

## Setting the label and content

- **MenuStyleConfiguration.Label**: A type-erased label of a menu.
- **MenuStyleConfiguration.Content**: A type-erased content of a menu.

## Styling menus

- **menuStyle(_:)**: Sets the style for menus within this view.
- **MenuStyle**: A type that applies standard interaction behavior and a custom appearance to all menus within a view hierarchy.

