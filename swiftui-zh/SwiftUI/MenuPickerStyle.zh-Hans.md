---
来源： https://developer.apple.com/documentation/SwiftUI/MenuPickerStyle
抓取时间： 2025-12-03T06:09:22Z
---

# MenuPickerStyle

**Structure**

选取器样式，当用户按下按钮时以菜单形式显示选项，当嵌套在较大的菜单中时以子菜单形式显示选项。

### 声明

```swift
struct MenuPickerStyle
```

## 概览

您也可以使用 [menu](PickerStyle/menu.zh-Hans.md) 构建这种样式。

## 创建拾取器样式

- **init()**：创建菜单选取器样式。

## 支持类型

- **DefaultPickerStyle**：默认选取器样式，基于选取器的上下文。
- **InlinePickerStyle**：一个 `PickerStyle`，其中每个选项都与当前容器中的其他视图并列显示。
- **NavigationLinkPickerStyle**：由导航链接表示的选取器样式，通过推送列表样式的选取器视图来显示选项。
- **PalettePickerStyle**：以一排紧凑元素显示选项的选取器样式。
- **RadioGroupPickerStyle**：以一组单选按钮的形式显示选项的选取器样式。
- **SegmentedPickerStyle**：在分段控件中显示选项的选取器样式。
- **WheelPickerStyle**：一种选取器样式，它以可滚动滚轮的形式显示选项，滚轮上显示所选选项和邻近的几个选项。

## 符合

- 选取器样式


---
source: https://developer.apple.com/documentation/SwiftUI/MenuPickerStyle
crawled: 2025-12-03T06:09:22Z
---

# MenuPickerStyle

**Structure**

A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.

## Declaration

```swift
struct MenuPickerStyle
```

## Overview

You can also use [menu](PickerStyle/menu.zh-Hans.md) to construct this style.

## Creating the picker style

- **init()**: Creates a menu picker style.

## Supporting types

- **DefaultPickerStyle**: The default picker style, based on the picker’s context.
- **InlinePickerStyle**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **NavigationLinkPickerStyle**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **PalettePickerStyle**: A picker style that presents the options as a row of compact elements.
- **RadioGroupPickerStyle**: A picker style that presents the options as a group of radio buttons.
- **SegmentedPickerStyle**: A picker style that presents the options in a segmented control.
- **WheelPickerStyle**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

## Conforms To

- PickerStyle

