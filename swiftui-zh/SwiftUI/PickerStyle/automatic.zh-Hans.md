---
来源： https://developer.apple.com/documentation/SwiftUI/PickerStyle/automatic
抓取时间： 2025-12-03T06:09:15Z
---

# 自动

**类型属性**

基于拾取器上下文的默认拾取器样式。

## 声明

```swift
static var automatic: DefaultPickerStyle { get }
```

## 讨论

使用默认拾取器样式的拾取器的显示方式主要取决于其所在的平台和视图类型。例如，在标准视图中，各平台的默认选取器样式如下：

- 在 iOS 和 watchOS 上，默认为滚轮。
- 在 macOS 上，默认为弹出按钮。
- 在 tvOS 上，默认为分段控件。

在设置选取器外观时，默认选取器样式还可能考虑其他因素，例如选取器是否出现在容器视图中。

您可以覆盖选取器的样式。要将默认样式应用于选取器或包含选取器的视图，请使用[pickerStyle(_:)](../View/pickerStyle.zh-Hans.md)修饰符。

## 获取内置拾取器样式

- **inline**：一个 `PickerStyle`，其中每个选项都与当前容器中的其他视图并列显示。
- **menu**：选取器样式，当用户按下按钮时，以菜单的形式显示选项，当嵌套在较大的菜单中时，则以子菜单的形式显示选项。
- **navigationLink**：由导航链接表示的选取器样式，通过推动列表样式的选取器视图来显示选项。
- **palette**：以一排紧凑元素显示选项的选取器样式。
- **radioGroup**：以一组单选按钮的形式显示选项的选取器样式。
- **segmented**：在分段控件中显示选项的选取器样式。
- **wheel**：一种选取器样式，它以可滚动滚轮的形式显示选项，滚轮上显示所选选项和邻近的几个选项。


---
source: https://developer.apple.com/documentation/SwiftUI/PickerStyle/automatic
crawled: 2025-12-03T06:09:15Z
---

# automatic

**Type Property**

The default picker style, based on the picker’s context.

## Declaration

```swift
static var automatic: DefaultPickerStyle { get }
```

## Discussion

How a picker using the default picker style appears largely depends on the platform and the view type in which it appears. For example, in a standard view, the default picker styles by platform are:

- On iOS and watchOS the default is a wheel.
- On macOS, the default is a pop-up button.
- On tvOS, the default is a segmented control.

The default picker style may also take into account other factors — like whether the picker appears in a container view — when setting the appearance of a picker.

You can override a picker’s style. To apply the default style to a picker, or to a view that contains pickers, use the [pickerStyle(_:)](../View/pickerStyle.zh-Hans.md) modifier.

## Getting built-in picker styles

- **inline**: A `PickerStyle` where each option is displayed inline with other views in the current container.
- **menu**: A picker style that presents the options as a menu when the user presses a button, or as a submenu when nested within a larger menu.
- **navigationLink**: A picker style represented by a navigation link that presents the options by pushing a List-style picker view.
- **palette**: A picker style that presents the options as a row of compact elements.
- **radioGroup**: A picker style that presents the options as a group of radio buttons.
- **segmented**: A picker style that presents the options in a segmented control.
- **wheel**: A picker style that presents the options in a scrollable wheel that shows the selected option and a few neighboring options.

