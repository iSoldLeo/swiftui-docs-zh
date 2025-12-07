---
来源： https://developer.apple.com/documentation/SwiftUI/MenuBarExtraStyle
抓取时间： 2025-12-02T17:20:57Z
---

# MenuBarExtraStyle

**Protocol**

菜单栏额外场景的外观和行为规范。

## 声明

```swift
protocol MenuBarExtraStyle
```

## 获取菜单栏额外样式

- **automatic**：默认菜单栏额外样式。
- **menu**：菜单栏额外样式，可将其内容渲染为从菜单栏图标下拉的菜单。
- **window**：在弹出窗口中显示其内容的菜单栏额外样式。

## 支持类型

- **AutomaticMenuBarExtraStyle**：默认的菜单栏额外样式。您也可以使用 [automatic](MenuBarExtraStyle/automatic.zh-Hans.md) 构建此样式。
- **PullDownMenuBarExtraStyle**：菜单栏额外样式，可将其内容渲染为从菜单栏图标下拉的菜单。
- **WindowMenuBarExtraStyle**：在弹出窗口中显示其内容的菜单栏额外样式。

## 创建菜单栏额外样式

- **MenuBarExtra**：将自己渲染为系统菜单栏中一个持久控件的场景。
- **menuBarExtraStyle(_:)**：设置此场景创建的菜单栏额外控件的样式。

## 符合类型

- 自动菜单栏额外样式
- 下拉菜单栏额外样式
- 窗口菜单栏额外样式


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtraStyle
crawled: 2025-12-02T17:20:57Z
---

# MenuBarExtraStyle

**Protocol**

A specification for the appearance and behavior of a menu bar extra scene.

## Declaration

```swift
protocol MenuBarExtraStyle
```

## Getting menu bar extra styles

- **automatic**: The default menu bar extra style.
- **menu**: A menu bar extra style that renders its contents as a menu that pulls down from the icon in the menu bar.
- **window**: A menu bar extra style that renders its contents in a popover-like window.

## Supporting types

- **AutomaticMenuBarExtraStyle**: The default menu bar extra style. You can also use [automatic](MenuBarExtraStyle/automatic.zh-Hans.md) to construct this style.
- **PullDownMenuBarExtraStyle**: A menu bar extra style that renders its contents as a menu that pulls down from the icon in the menu bar.
- **WindowMenuBarExtraStyle**: A menu bar extra style that renders its contents in a popover-like window.

## Creating a menu bar extra

- **MenuBarExtra**: A scene that renders itself as a persistent control in the system menu bar.
- **menuBarExtraStyle(_:)**: Sets the style for menu bar extra created by this scene.

## Conforming Types

- AutomaticMenuBarExtraStyle
- PullDownMenuBarExtraStyle
- WindowMenuBarExtraStyle

