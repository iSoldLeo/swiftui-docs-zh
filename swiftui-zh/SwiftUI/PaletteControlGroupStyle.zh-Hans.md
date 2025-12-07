---
来源： https://developer.apple.com/documentation/SwiftUI/PaletteControlGroupStyle
抓取时间： 2025-12-03T06:11:35Z
---

# PaletteControlGroupStyle

**Structure**

以调色板形式显示内容的控制组样式。

## 声明

```swift
struct PaletteControlGroupStyle
```

## 概览

使用 [palette](ControlGroupStyle/palette.zh-Hans.md) 构建此样式。

## 创建控制组样式

- **init()**：创建调色板控制组样式。

## 支持类型

- **AutomaticControlGroupStyle**：默认控制组样式。
- **CompactMenuControlGroupStyle**：当用户按下控件时，控件组样式会以紧凑菜单的形式显示其内容，当控件嵌套在较大的菜单中时，则以子菜单的形式显示其内容。
- **MenuControlGroupStyle**：当用户按下控件时，控件组样式会以菜单的形式显示其内容，当控件嵌套在更大的菜单中时，则以子菜单的形式显示其内容。
- **NavigationControlGroupStyle**：导航控件组样式。

## 符合

- 控制组样式


---
source: https://developer.apple.com/documentation/SwiftUI/PaletteControlGroupStyle
crawled: 2025-12-03T06:11:35Z
---

# PaletteControlGroupStyle

**Structure**

A control group style that presents its content as a palette.

## Declaration

```swift
struct PaletteControlGroupStyle
```

## Overview

Use [palette](ControlGroupStyle/palette.zh-Hans.md) to construct this style.

## Creating the control group style

- **init()**: Creates a palette control group style.

## Supporting types

- **AutomaticControlGroupStyle**: The default control group style.
- **CompactMenuControlGroupStyle**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **MenuControlGroupStyle**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **NavigationControlGroupStyle**: The navigation control group style.

## Conforms To

- ControlGroupStyle

