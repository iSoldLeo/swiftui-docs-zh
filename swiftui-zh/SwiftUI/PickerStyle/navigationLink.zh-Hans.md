---
来源： https://developer.apple.com/documentation/SwiftUI/PickerStyle/navigationLink
抓取时间： 2025-12-03T06:09:17Z
---

# 导航链接

**类型属性**

由导航链接表示的选取器样式，通过推送列表样式的选取器视图来显示选项。

## 声明

```swift
static var navigationLink: NavigationLinkPickerStyle { get }
```

## 讨论

在导航堆栈中，首选默认的[menu](menu.zh-Hans.md)样式。当您有大量选项或您的设计通过推入堆栈来更好地表达时，请考虑使用导航链接样式。

要将此样式应用于选取器或包含选取器的视图，请使用[pickerStyle(_:)](../View/pickerStyle.zh-Hans.md)修饰符。

## 获取内置拾取器样式

- **automatic**：基于选取器上下文的默认选取器样式。
- **inline**：一个 `PickerStyle`，其中每个选项都与当前容器中的其他视图并列显示。
- **menu**：选取器样式，当用户按下按钮时，以菜单的形式显示选项，当嵌套在较大的菜单中时，则以子菜单的形式显示选项。
- **palette**：选取器样式，将选项显示为一排紧凑的元素。
- **radioGroup**：以一组单选按钮的形式显示选项的选取器样式。
- **segmented**：在分段控件中显示选项的选取器样式。
- **wheel**：一种选取器样式，以可滚动的滚轮显示选项，滚轮上显示所选选项和邻近的几个选项。


---
source: https://developer.apple.com/documentation/SwiftUI/PickerStyle/navigationLink
crawled: 2025-12-03T06:09:17Z
---

# navigationLink

**Type Property**

A picker style represented by a navigation link that presents the options by pushing a List-style picker view.

## Declaration

```swift
static var navigationLink: NavigationLinkPickerStyle { get }
```

## Discussion

In navigation stacks, prefer the default [menu](menu.zh-Hans.md) style. Consider the navigation link style when you have a large number of options or your design is better expressed by pushing onto a stack.

To apply this style to a picker, or to a view that contains pickers, use the [pickerStyle(_:)](../View/pickerStyle.zh-Hans.md) modifier.

## Getting built-in picker styles

- **automatic**: The default picker style, based on the picker’s context.
- **inline**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **menu**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **palette**: A picker style that presents the options as a row of compact elements.
- **radioGroup**: A picker style that presents the options as a group of radio buttons.
- **segmented**: A picker style that presents the options in a segmented control.
- **wheel**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

