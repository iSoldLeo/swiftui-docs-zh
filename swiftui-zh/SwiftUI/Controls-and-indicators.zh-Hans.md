---

来源：https://developer.apple.com/documentation/SwiftUI/Controls-and-indicators
抓取时间：2025-12-02T16:02:50Z

---

# 控件和指示器

**API 集合**

显示值并获取用户选择。

## 概述

SwiftUI 提供控件，支持针对不同平台和上下文的用户交互。例如，用户可以使用按钮和链接发起事件，或者使用不同类型的选择器从一组离散值中进行选择。您还可以使用进度视图和仪表盘等指示器向用户显示信息。

在构建自定义视图时，请使用这些内置控件和指示器，并根据应用的用户界面需求设置样式。有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/menus-and-actions]、[doc://com.apple.documentation/design/Human-Interface-Guidelines/selection-and-input] 和 [doc://com.apple.documentation/design/Human-Interface-Guidelines/status]。

## 创建按钮

- **Button**：用于启动操作的控件。

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。

- **buttonRepeatBehavior(_:)**：设置此视图中的按钮在长时间交互后是否应重复触发其操作。

- **buttonRepeatBehavior**：设置具有此关联环境的按钮在长时间交互后是否应重复触发其操作。

- **ButtonBorderShape**：用于绘制按钮边框的形状。

- **ButtonRole**：描述按钮用途的值。

- **ButtonRepeatBehavior**：用于控制按钮操作重复性的选项。

- **ButtonSizing**：`Button` 和其他类似按钮控件的大小调整行为。

## 创建特殊用途按钮

- **EditButton**：切换编辑模式环境值的按钮。

- **PasteButton**：从剪贴板读取项目并将其传递给闭包的系统按钮。

- **RenameButton**：触发标准重命名操作的按钮。

## 链接到其他内容

- **Link**：用于导航到 URL 的控件。

- **ShareLink**：控制共享演示的视图。

- **SharePreview**：要在共享预览中显示的类型表示。

- **TextFieldLink**：按下时请求用户输入文本的控件。

- **HelpLink**：具有标准外观的按钮，用于打开应用程序特定的帮助文档。

## 获取数值输入

- **Slider**：用于从有界线性值范围内选择值的控件。

- **Stepper**：执行递增和递减操作的控件。

- **Toggle**：用于在开和关状态之间切换的控件。

- **toggleStyle(_:)**：设置视图层次结构中切换按钮的样式。

## 从一组选项中进行选择

- **Picker**：用于从一组互斥值中进行选择的控件。

- **pickerStyle(_:)**：设置此视图中选择器的样式。

- **horizontalRadioGroupLayout()**：设置此视图中单选按钮组样式选择器的样式，使其水平排列，单选按钮位于布局内。

- **defaultWheelPickerItemHeight(_:)**：设置默认的滚轮式选择器项高度。

- **defaultWheelPickerItemHeight**：滚轮式选择器（例如日期选择器）中项目的默认高度。

- **paletteSelectionEffect(_:)**：指定要应用于调色板项的选择效果。

- **PaletteSelectionEffect**：要应用于调色板项的选择效果。

## 选择日期

- **DatePicker**：用于选择绝对日期的控件。

- **datePickerStyle(_:)**：设置此视图中日期选择器的样式。

- **MultiDatePicker**：用于选择多个日期的控件。

- **calendar**：视图在处理日期时应使用的当前日历。

- **timeZone**：视图在处理日期时应使用的当前时区。

## 选择颜色

- **ColorPicker**：用于从系统颜色选择器 UI 中选择颜色的控件。

## 指示值

- **Gauge**：显示某个范围内值的视图。

- **gaugeStyle(_:)**：设置此视图中仪表盘的样式。

- **ProgressView**：显示任务完成进度的视图。

- **progressViewStyle(_:)**：设置此视图中进度条的样式。

- **DefaultDateProgressLabel**：日期相关进度条视图中当前值标签的默认类型。

- **DefaultButtonLabel**：按钮的默认标签。

## 指示内容缺失

- **ContentUnavailableView**：当应用内容对用户不可用时，显示包含标签和附加内容的界面。

## 提供触觉反馈

- **sensoryFeedback(_:trigger:)**：当提供的 `trigger` 值发生变化时，播放指定的 `feedback`。

- **sensoryFeedback(trigger:_:)**：当提供的 `trigger` 值发生变化后，从 `feedback` 闭包返回时播放反馈。

- **sensoryFeedback(_:trigger:condition:)**：当提供的 `trigger` 值发生变化且 `condition` 闭包返回 `true` 时，播放指定的 `feedback`。

- **SensoryFeedback**：表示可以播放的触觉和/或音频反馈类型。

## 尺寸控制

- **controlSize(_:)**：设置此视图中控件的大小。

- **controlSize**：应用于视图中控件的大小。

- **ControlSize**：您可以为视图中的控件设置尺寸类别，例如常规或小型。

## 视图

- **视图基础**：使用视图层次结构定义应用程序的视觉元素。

- **视图配置**：调整层次结构中视图的特性。

- **视图样式**：为不同类型的视图应用内置和自定义的外观和行为。

- **Animations**：响应状态更改，实现流畅的视觉更新。

- **文本输入和输出**：显示格式化文本并接收用户输入的文本。

- **Images**：向应用程序的用户界面添加图像和符号。

- **菜单和命令**：提供节省空间且上下文相关的命令和控件访问方式。

- **Shapes**：使用颜色、渐变或其他图案描绘并填充内置和自定义形状。

- **绘图和图形**：使用图形效果和自定义绘图增强您的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Controls-and-indicators
crawled: 2025-12-02T16:02:50Z
---

# Controls and indicators

**API Collection**

Display values and get user selections.

## Overview

SwiftUI provides controls that enable user interaction specific to each platform and context. For example, people can initiate events with buttons and links, or choose among a set of discrete values with different kinds of pickers. You can also display information to the user with indicators like progress views and gauges.



Use these built-in controls and indicators when composing custom views, and style them to match the needs of your app’s user interface. For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/menus-and-actions], [doc://com.apple.documentation/design/Human-Interface-Guidelines/selection-and-input], and [doc://com.apple.documentation/design/Human-Interface-Guidelines/status] in the Human Interface Guidelines.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

## Creating special-purpose buttons

- **EditButton**: A button that toggles the edit mode environment value.
- **PasteButton**: A system button that reads items from the pasteboard and delivers it to a closure.
- **RenameButton**: A button that triggers a standard rename action.

## Linking to other content

- **Link**: A control for navigating to a URL.
- **ShareLink**: A view that controls a sharing presentation.
- **SharePreview**: A representation of a type to display in a share preview.
- **TextFieldLink**: A control that requests text input from the user when pressed.
- **HelpLink**: A button with a standard appearance that opens app-specific help documentation.

## Getting numeric inputs

- **Slider**: A control for selecting a value from a bounded linear range of values.
- **Stepper**: A control that performs increment and decrement actions.
- **Toggle**: A control that toggles between on and off states.
- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.

## Choosing from a set of options

- **Picker**: A control for selecting from a set of mutually exclusive values.
- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **horizontalRadioGroupLayout()**: Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.
- **defaultWheelPickerItemHeight(_:)**: Sets the default wheel-style picker item height.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **paletteSelectionEffect(_:)**: Specifies the selection effect to apply to a palette item.
- **PaletteSelectionEffect**: The selection effect to apply to a palette item.

## Choosing dates

- **DatePicker**: A control for selecting an absolute date.
- **datePickerStyle(_:)**: Sets the style for date pickers within this view.
- **MultiDatePicker**: A control for picking multiple dates.
- **calendar**: The current calendar that views should use when handling dates.
- **timeZone**: The current time zone that views should use when handling dates.

## Choosing a color

- **ColorPicker**: A control used to select a color from the system color picker UI.

## Indicating a value

- **Gauge**: A view that shows a value within a range.
- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **ProgressView**: A view that shows the progress toward completion of a task.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **DefaultDateProgressLabel**: The default type of the current value label when used by a date-relative progress view.
- **DefaultButtonLabel**: The default label to use for a button.

## Indicating missing content

- **ContentUnavailableView**: An interface, consisting of a label and additional content, that you display when the content of your app is unavailable to users.

## Providing haptic feedback

- **sensoryFeedback(_:trigger:)**: Plays the specified `feedback` when the provided `trigger` value changes.
- **sensoryFeedback(trigger:_:)**: Plays feedback when returned from the `feedback` closure after the provided `trigger` value changes.
- **sensoryFeedback(_:trigger:condition:)**: Plays the specified `feedback` when the provided `trigger` value changes and the `condition` closure returns `true`.
- **SensoryFeedback**: Represents a type of haptic and/or audio feedback that can be played.

## Sizing controls

- **controlSize(_:)**: Sets the size for controls within this view.
- **controlSize**: The size to apply to controls within a view.
- **ControlSize**: The size classes, like regular or small, that you can apply to controls within a view.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

