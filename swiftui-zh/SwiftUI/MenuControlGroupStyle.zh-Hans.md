---
来源： https://developer.apple.com/documentation/SwiftUI/MenuControlGroupStyle
抓取时间： 2025-12-03T06:11:34Z
---

# MenuControlGroupStyle

**Structure**

控件组样式，当用户按下控件时将其内容显示为菜单，当嵌套在较大的菜单中时则显示为子菜单。

### 声明

```swift
struct MenuControlGroupStyle
```

## 概览

使用 [menu](ControlGroupStyle/menu.zh-Hans.md) 构建此样式。

## 创建控制组样式

- **init()**：创建菜单控制组样式。

## 支持类型

- **AutomaticControlGroupStyle**：默认控制组样式。
- **CompactMenuControlGroupStyle**：当用户按下控件时，控件组样式会以紧凑菜单的形式显示其内容，当控件嵌套在较大的菜单中时，则以子菜单的形式显示其内容。
- **NavigationControlGroupStyle**：导航控件组样式。
- **PaletteControlGroupStyle**：导航控件组样式：以调色板形式显示内容的控制组样式。

## 符合

- 控制组样式


---
source: https://developer.apple.com/documentation/SwiftUI/MenuControlGroupStyle
crawled: 2025-12-03T06:11:34Z
---

# MenuControlGroupStyle

**Structure**

A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.

## Declaration

```swift
struct MenuControlGroupStyle
```

## Overview

Use [menu](ControlGroupStyle/menu.zh-Hans.md) to construct this style.

## Creating the control group style

- **init()**: Creates a menu control group style.

## Supporting types

- **AutomaticControlGroupStyle**: The default control group style.
- **CompactMenuControlGroupStyle**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **NavigationControlGroupStyle**: The navigation control group style.
- **PaletteControlGroupStyle**: A control group style that presents its content as a palette.

## Conforms To

- ControlGroupStyle

