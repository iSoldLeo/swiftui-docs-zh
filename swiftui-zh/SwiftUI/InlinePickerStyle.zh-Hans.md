--- 来源：https://developer.apple.com/documentation/SwiftUI/InlinePickerStyle
抓取时间：2025-12-03T06:09:21Z

---

# InlinePickerStyle

**Structure**

一个 `PickerStyle` 样式，其中每个选项都与其他视图一起内联显示在当前容器中。

## 声明

```swift
struct InlinePickerStyle
```

## 概述

您也可以使用 [inline](PickerStyle/inline.zh-Hans.md) 来构建此样式。

## 创建选择器样式

- **init()**：创建一个内联选择器样式。

## 支持的类型

- **DefaultPickerStyle**：基于选择器上下文的默认选择器样式。

- **MenuPickerStyle**：一种选择器样式，用户按下按钮时，选项以菜单形式呈现；嵌套在更大的菜单中时，选项以子菜单形式呈现。

- **NavigationLinkPickerStyle**：一种选择器样式，通过导航链接点击列表式选择器视图来呈现选项。

- **PalettePickerStyle**：一种选择器样式，选项以一行紧凑元素的形式呈现。

- **RadioGroupPickerStyle**：一种选择器样式，选项以一组单选按钮的形式呈现。

- **SegmentedPickerStyle**：一种选择器样式，选项以分段控件的形式呈现。

- **WheelPickerStyle**：一种选择器样式，选项以可滚动的滚轮形式呈现，滚轮上显示选定的选项及其几个相邻选项。

## 符合以下规范

- PickerStyle


---
source: https://developer.apple.com/documentation/SwiftUI/InlinePickerStyle
crawled: 2025-12-03T06:09:21Z
---

# InlinePickerStyle

**Structure**

A `PickerStyle` where each option is displayed inline with other views in the current container.

## Declaration

```swift
struct InlinePickerStyle
```

## Overview

You can also use [inline](PickerStyle/inline.zh-Hans.md) to construct this style.

## Creating the picker style

- **init()**: Creates an inline picker style.

## Supporting types

- **DefaultPickerStyle**: The default picker style, based on the picker’s context.
- **MenuPickerStyle**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **NavigationLinkPickerStyle**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **PalettePickerStyle**: A picker style that presents the options as a row of compact elements.
- **RadioGroupPickerStyle**: A picker style that presents the options as a group of radio buttons.
- **SegmentedPickerStyle**: A picker style that presents the options in a segmented control.
- **WheelPickerStyle**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

## Conforms To

- PickerStyle

