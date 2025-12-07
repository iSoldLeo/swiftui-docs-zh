---
来源： https://developer.apple.com/documentation/SwiftUI/PickerStyle/inline
抓取时间： 2025-12-03T06:09:15Z
---

# 内联

**类型属性**

一个 `PickerStyle`，其中每个选项都与当前容器中的其他视图并列显示。

## 声明

```swift
static var inline: InlinePickerStyle { get }
```

## 获取内置拾取器样式

- **automatic**：基于选取器上下文的默认选取器样式。
- **menu**：选取器样式，当用户按下按钮时以菜单形式显示选项，当嵌套在较大的菜单中时以子菜单形式显示选项。
- **navigationLink**：由导航链接表示的选取器样式，通过推动列表样式的选取器视图来显示选项。
- **palette**：以一排紧凑元素显示选项的选取器样式。
- **radioGroup**：以一组单选按钮的形式显示选项的选取器样式。
- **segmented**：在分段控件中显示选项的选取器样式。
- **wheel**：一种选取器样式，它以可滚动滚轮的形式显示选项，滚轮上显示所选选项和邻近的几个选项。


---
source: https://developer.apple.com/documentation/SwiftUI/PickerStyle/inline
crawled: 2025-12-03T06:09:15Z
---

# inline

**Type Property**

A `PickerStyle` where each option is displayed inline with other views in the current container.

## Declaration

```swift
static var inline: InlinePickerStyle { get }
```

## Getting built-in picker styles

- **automatic**: The default picker style, based on the picker’s context.
- **menu**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **navigationLink**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **palette**: A picker style that presents the options as a row of compact elements.
- **radioGroup**: A picker style that presents the options as a group of radio buttons.
- **segmented**: A picker style that presents the options in a segmented control.
- **wheel**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

