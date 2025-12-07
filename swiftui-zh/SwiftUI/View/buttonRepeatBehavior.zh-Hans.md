--- 来源：https://developer.apple.com/documentation/SwiftUI/View/buttonRepeatBehavior(_:)

抓取时间：2025-11-30T21:21:04Z

---

# buttonRepeatBehavior(_:)

**实例方法**

设置此视图中的按钮在长时间交互后是否应重复执行其操作。

## 声明

```swift
nonisolated func buttonRepeatBehavior(_ behavior: ButtonRepeatBehavior) -> some View

```

## 参数

- **behavior**：值为 `enabled` 表示按钮应启用重复行为，值为 `disabled` 表示按钮应禁用重复行为。

## 说明

适用于递增或递减某个值或执行其他本质上是迭代操作的按钮。诸如按住按钮、按住按钮的快捷键或在按钮获得焦点时按住空格键等交互操作将触发此重复行为。

```swift
Button {
    playbackSpeed.advance(by: 1)
} label: {
    Label("Speed up", systemImage: "hare")
}
.buttonRepeatBehavior(.enabled)
```

此设置会影响所有系统按钮样式，并自动影响自定义的`ButtonStyle`兼容类型。此设置不会自动应用于自定义的`PrimitiveButtonStyle`兼容类型，应使用`EnvironmentValues.buttonRepeatBehavior`值来根据需要调整其自定义手势。

## 创建按钮

- **Button**：用于启动操作的控件。

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。

- **buttonRepeatBehavior**：此关联环境中的按钮是否应在长时间交互后重复触发其操作。

- **ButtonBorderShape**：用于绘制按钮边框的形状。

- **ButtonRole**：描述按钮用途的值。

- **ButtonRepeatBehavior**：控制按钮操作重复性的选项。

- **ButtonSizing**：`Button` 和其他类似按钮的控件的大小调整行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/buttonRepeatBehavior(_:)
crawled: 2025-11-30T21:21:04Z
---

# buttonRepeatBehavior(_:)

**Instance Method**

Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.

## Declaration

```swift
nonisolated func buttonRepeatBehavior(_ behavior: ButtonRepeatBehavior) -> some View

```

## Parameters

- **behavior**: A value of `enabled` means that buttons should enable repeating behavior and a value of `disabled` means that buttons should disallow repeating behavior.

## Discussion

Apply this to buttons that increment or decrement a value or perform some other inherently iterative operation. Interactions such as pressing-and-holding on the button, holding the button’s keyboard shortcut, or holding down the space key while the button is focused will trigger this repeat behavior.

```swift
Button {
    playbackSpeed.advance(by: 1)
} label: {
    Label("Speed up", systemImage: "hare")
}
.buttonRepeatBehavior(.enabled)
```

This affects all system button styles, as well as automatically affects custom `ButtonStyle` conforming types. This does not automatically apply to custom `PrimitiveButtonStyle` conforming types, and the `EnvironmentValues.buttonRepeatBehavior` value should be used to adjust their custom gestures as appropriate.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

