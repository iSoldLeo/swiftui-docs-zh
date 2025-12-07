---
来源： https://developer.apple.com/documentation/SwiftUI/PickerStyle/radioGroup
抓取时间： 2025-12-03T06:09:18Z
---

# radioGroup

**类型属性**

一种选取器样式，以一组单选按钮的形式显示选项。

## 声明

```swift
static var radioGroup: RadioGroupPickerStyle { get }
```

## 讨论

有 2 到 5 个选项时使用这种样式。当选项超过五个时，考虑使用 [menu](menu.zh-Hans.md)。

对于每个选项的标签，使用句子式大写，不使用句末标点符号，如句号或冒号。

要将此样式应用于选取器或包含选取器的视图，请使用[pickerStyle(_:)](../View/pickerStyle.zh-Hans.md)修饰符。

## 获取内置拾取器样式

- **automatic**：基于选取器上下文的默认选取器样式。
- **inline**：一个 `PickerStyle`，其中每个选项都与当前容器中的其他视图并列显示。
- **menu**：选取器样式，当用户按下按钮时，以菜单的形式显示选项，当嵌套在较大的菜单中时，则以子菜单的形式显示选项。
- **navigationLink**：由导航链接表示的选取器样式，通过推动列表样式的选取器视图来显示选项。
- **palette**：以一排紧凑元素显示选项的选取器样式。
- **segmented**：在分段控件中显示选项的选取器样式。
- **wheel**：一种选取器样式，以可滚动的滚轮显示选项，滚轮上显示所选选项和邻近的几个选项。


---
source: https://developer.apple.com/documentation/SwiftUI/PickerStyle/radioGroup
crawled: 2025-12-03T06:09:18Z
---

# radioGroup

**Type Property**

A picker style that presents the options as a group of radio buttons.

## Declaration

```swift
static var radioGroup: RadioGroupPickerStyle { get }
```

## Discussion

Use this style when there are two to five options. Consider using [menu](menu.zh-Hans.md) when there are more than five options.

For each option’s label, use sentence-style capitalization without ending punctuation, like a period or colon.

To apply this style to a picker, or to a view that contains pickers, use the [pickerStyle(_:)](../View/pickerStyle.zh-Hans.md) modifier.

## Getting built-in picker styles

- **automatic**: The default picker style, based on the picker’s context.
- **inline**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **menu**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **navigationLink**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **palette**: A picker style that presents the options as a row of compact elements.
- **segmented**: A picker style that presents the options in a segmented control.
- **wheel**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

