--- 来源：https://developer.apple.com/documentation/SwiftUI/PickerStyle
抓取时间：2025-12-02T17:33:05Z

---

# PickerStyle

**Protocol**

一种类型，用于指定视图层级结构中所有选择器的外观和交互方式。

## 声明

```swift
protocol PickerStyle
```

## 获取内置选择器样式

- **automatic**：基于选择器上下文的默认选择器样式。

- **inline**：一种 `PickerStyle` 样式，其中每个选项都与其他视图一起显示在当前容器中。

- **menu**：一种选择器样式，用户按下按钮时，选项以菜单形式呈现；嵌套在更大的菜单中时，选项以子菜单形式呈现。

- **navigationLink**：一种选择器样式，通过导航链接点击列表式选择器视图来呈现选项。

- **palette**：一种选择器样式，选项以一行紧凑元素的形式呈现。

- **radioGroup**：一种选择器样式，选项以一组单选按钮的形式呈现。

- **segmented**：一种选择器样式，选项以分段控件的形式呈现。

- **wheel**：一种选择器样式，选项以可滚动的滚轮形式呈现，滚轮上显示选定的选项及其几个相邻选项。

## 支持的类型

- **DefaultPickerStyle**：默认选择器样式，基于选择器的上下文。

- **InlinePickerStyle**：`PickerStyle`，其中每个选项都与其他视图一起显示在当前容器中。

- **MenuPickerStyle**：一种选择器样式，当用户按下按钮时，选项以菜单形式呈现；当嵌套在更大的菜单中时，选项以子菜单形式呈现。

- **NavigationLinkPickerStyle**：一种选择器样式，通过导航链接推送列表样式的选择器视图来呈现选项。

- **PalettePickerStyle**：一种选择器样式，将选项呈现为一行紧凑的元素。

- **RadioGroupPickerStyle**：一种选择器样式，将选项呈现为一组单选按钮。

- **SegmentedPickerStyle**：一种选择器样式，以分段控件的形式呈现选项。

- **WheelPickerStyle**：一种选择器样式，以可滚动的滚轮形式呈现选项，滚轮上会显示选定的选项及其几个相邻选项。

## 已弃用样式

- **PopUpButtonPickerStyle**：一种选择器样式，用户按下按钮时，选项会以菜单的形式呈现。

## 选择器样式

- **pickerStyle(_:)**：设置此视图中所有选择器的样式。

- **datePickerStyle(_:)**：设置此视图中所有日期选择器的样式。

- **DatePickerStyle**：一种类型，用于指定视图层次结构中所有日期选择器的外观和交互方式。

## 符合规范的类型

- DefaultPickerStyle

- InlinePickerStyle

- MenuPickerStyle

- NavigationLinkPickerStyle

- PalettePickerStyle

- PopUpButtonPickerStyle

- RadioGroupPickerStyle

- SegmentedPickerStyle

- WheelPickerStyle


---
source: https://developer.apple.com/documentation/SwiftUI/PickerStyle
crawled: 2025-12-02T17:33:05Z
---

# PickerStyle

**Protocol**

A type that specifies the appearance and interaction of all pickers within a view hierarchy.

## Declaration

```swift
protocol PickerStyle
```

## Getting built-in picker styles

- **automatic**: The default picker style, based on the picker’s context.
- **inline**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **menu**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **navigationLink**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **palette**: A picker style that presents the options as a row of compact elements.
- **radioGroup**: A picker style that presents the options as a group of radio buttons.
- **segmented**: A picker style that presents the options in a segmented control.
- **wheel**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

## Supporting types

- **DefaultPickerStyle**: The default picker style, based on the picker’s context.
- **InlinePickerStyle**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **MenuPickerStyle**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **NavigationLinkPickerStyle**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **PalettePickerStyle**: A picker style that presents the options as a row of compact elements.
- **RadioGroupPickerStyle**: A picker style that presents the options as a group of radio buttons.
- **SegmentedPickerStyle**: A picker style that presents the options in a segmented control.
- **WheelPickerStyle**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

## Deprecated styles

- **PopUpButtonPickerStyle**: A picker style that presents the options as a menu when the user presses a button.

## Styling pickers

- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **datePickerStyle(_:)**: Sets the style for date pickers within this view.
- **DatePickerStyle**: A type that specifies the appearance and interaction of all date pickers within a view hierarchy.

## Conforming Types

- DefaultPickerStyle
- InlinePickerStyle
- MenuPickerStyle
- NavigationLinkPickerStyle
- PalettePickerStyle
- PopUpButtonPickerStyle
- RadioGroupPickerStyle
- SegmentedPickerStyle
- WheelPickerStyle

