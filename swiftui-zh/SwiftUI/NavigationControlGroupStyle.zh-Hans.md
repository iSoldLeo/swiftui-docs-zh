---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationControlGroupStyle
抓取时间： 2025-12-03T06:11:35Z
---

# 导航控制组样式

**Structure**

导航控件组样式。

## 声明

```swift
struct NavigationControlGroupStyle
```

## 概览

您也可以使用 [navigation](ControlGroupStyle/navigation.zh-Hans.md) 构建这种样式。

## 创建控制组样式

- **init()**：创建导航控制组样式。

## 支持类型

- **AutomaticControlGroupStyle**：默认控制组样式。
- **CompactMenuControlGroupStyle**：当用户按下控件时，控件组样式会以紧凑菜单的形式显示其内容，当控件嵌套在较大的菜单中时，则以子菜单的形式显示其内容。
- **MenuControlGroupStyle**：当用户按下控件时，控件组样式会以菜单的形式显示其内容，当控件嵌套在更大的菜单中时，则以子菜单的形式显示其内容。
- **PaletteControlGroupStyle**：将内容显示为调色板的控件组样式。

## 符合

- 控制组样式


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationControlGroupStyle
crawled: 2025-12-03T06:11:35Z
---

# NavigationControlGroupStyle

**Structure**

The navigation control group style.

## Declaration

```swift
struct NavigationControlGroupStyle
```

## Overview

You can also use [navigation](ControlGroupStyle/navigation.zh-Hans.md) to construct this style.

## Creating the control group style

- **init()**: Creates a navigation control group style.

## Supporting types

- **AutomaticControlGroupStyle**: The default control group style.
- **CompactMenuControlGroupStyle**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **MenuControlGroupStyle**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **PaletteControlGroupStyle**: A control group style that presents its content as a palette.

## Conforms To

- ControlGroupStyle

