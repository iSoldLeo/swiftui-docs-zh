--- 来源：https://developer.apple.com/documentation/SwiftUI/WheelPickerStyle
抓取时间：2025-12-03T06:09:26Z

---

# WheelPickerStyle

**Structure**

一种选择器样式，它以可滚动的滚轮形式呈现选项，滚轮上会显示选中的选项以及几个相邻的选项。

## 声明

```swift
struct WheelPickerStyle
```

## 概述

您也可以使用 [wheel](PickerStyle/wheel.zh-Hans.md) 来构建此样式。

## 创建选择器样式

- **init()**：设置选择器样式，使其显示一个选项滚轮，供用户进行选择。

## 支持的类型

- **DefaultPickerStyle**：基于选择器上下文的默认选择器样式。

- **InlinePickerStyle**：一种 `PickerStyle` 样式，其中每个选项都与其他视图一起显示在当前容器中。

- **MenuPickerStyle**：一种选择器样式，当用户按下按钮时，选项以菜单形式呈现；当嵌套在更大的菜单中时，选项以子菜单形式呈现。

- **NavigationLinkPickerStyle**：一种选择器样式，通过导航链接推送列表样式的选择器视图来呈现选项。

- **PalettePickerStyle**：一种选择器样式，将选项呈现为一行紧凑的元素。

- **RadioGroupPickerStyle**：一种选择器样式，将选项呈现为一组单选按钮。

- **SegmentedPickerStyle**：一种选择器样式，将选项呈现为分段控件。

## 符合以下规范

- PickerStyle


---
source: https://developer.apple.com/documentation/SwiftUI/WheelPickerStyle
crawled: 2025-12-03T06:09:26Z
---

# WheelPickerStyle

**Structure**

A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

## Declaration

```swift
struct WheelPickerStyle
```

## Overview

You can also use [wheel](PickerStyle/wheel.zh-Hans.md) to construct this style.

## Creating the picker style

- **init()**: Sets the picker style to display an item wheel from which the user makes a selection.

## Supporting types

- **DefaultPickerStyle**: The default picker style, based on the picker’s context.
- **InlinePickerStyle**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **MenuPickerStyle**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **NavigationLinkPickerStyle**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **PalettePickerStyle**: A picker style that presents the options as a row of compact elements.
- **RadioGroupPickerStyle**: A picker style that presents the options as a group of radio buttons.
- **SegmentedPickerStyle**: A picker style that presents the options in a segmented control.

## Conforms To

- PickerStyle

