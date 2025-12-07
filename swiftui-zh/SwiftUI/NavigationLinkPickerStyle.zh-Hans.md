--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationLinkPickerStyle
抓取时间：2025-12-03T06:09:23Z

---

# NavigationLinkPickerStyle

**Structure**

一种选择器样式，通过导航链接来呈现选项，并推送一个列表样式的选择器视图。

## 声明

```swift
struct NavigationLinkPickerStyle
```

## 概述

在导航堆栈中，建议使用默认的 [menu](PickerStyle/menu.zh-Hans.md) 样式。当选项数量较多或您的设计更适合通过堆栈来表达时，请考虑使用导航链接样式。

您也可以使用 [navigationLink](PickerStyle/navigationLink.zh-Hans.md) 来构建此样式。

## 创建选择器样式

- **init()**：创建一个导航链接选择器样式。

## 支持的类型

- **DefaultPickerStyle**：默认选择器样式，基于选择器的上下文。

- **InlinePickerStyle**：`PickerStyle`，其中每个选项都与其他视图一起内联显示在当前容器中。

- **MenuPickerStyle**：一种选择器样式，当用户按下按钮时，选项以菜单形式呈现；当嵌套在更大的菜单中时，选项以子菜单形式呈现。

- **PalettePickerStyle**：一种选择器样式，将选项显示为一行紧凑的元素。

- **RadioGroupPickerStyle**：一种选择器样式，将选项显示为一组单选按钮。

- **SegmentedPickerStyle**：一种选择器样式，将选项显示为分段控件。

- **WheelPickerStyle**：一种选择器样式，以可滚动的滚轮形式呈现选项，滚轮上会显示选中的选项及其几个相邻选项。

## 符合以下规范

- PickerStyle


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLinkPickerStyle
crawled: 2025-12-03T06:09:23Z
---

# NavigationLinkPickerStyle

**Structure**

A picker style represented by a navigation link that presents the options by pushing a List-style picker view.

## Declaration

```swift
struct NavigationLinkPickerStyle
```

## Overview

In navigation stacks, prefer the default [menu](PickerStyle/menu.zh-Hans.md) style. Consider the navigation link style when you have a large number of options or your design is better expressed by pushing onto a stack.

You can also use [navigationLink](PickerStyle/navigationLink.zh-Hans.md) to construct this style.

## Creating the picker style

- **init()**: Creates a navigation link picker style.

## Supporting types

- **DefaultPickerStyle**: The default picker style, based on the picker’s context.
- **InlinePickerStyle**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **MenuPickerStyle**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **PalettePickerStyle**: A picker style that presents the options as a row of compact elements.
- **RadioGroupPickerStyle**: A picker style that presents the options as a group of radio buttons.
- **SegmentedPickerStyle**: A picker style that presents the options in a segmented control.
- **WheelPickerStyle**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

## Conforms To

- PickerStyle

