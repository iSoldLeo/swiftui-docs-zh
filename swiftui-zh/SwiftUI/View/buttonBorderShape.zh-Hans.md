--- 来源：https://developer.apple.com/documentation/SwiftUI/View/buttonBorderShape(_:)

抓取时间：2025-11-30T21:21:03Z

---

# buttonBorderShape(_:)

**实例方法**

设置此视图中按钮的边框形状。

## 声明

```swift
nonisolated func buttonBorderShape(_ shape: ButtonBorderShape) -> some View

```

## 参数

- **shape**：要使用的形状。

## 说明

边框形状用于绘制带边框按钮的边框。

边框形状会影响 [bordered](../PrimitiveButtonStyle/bordered.zh-Hans.md) 和 [borderedProminent](../PrimitiveButtonStyle/borderedProminent.zh-Hans.md) 样式的按钮。

## 创建按钮

- **Button**：用于启动操作的控件。

- **buttonStyle(_:)**：将此视图中的按钮样式设置为具有自定义外观和标准交互行为的按钮样式。

- **buttonRepeatBehavior(_:)**：设置此视图中的按钮在长时间交互后是否应重复触发其操作。

- **buttonRepeatBehavior**：设置与此关联环境中的按钮在长时间交互后是否应重复触发其操作。

- **ButtonBorderShape**：用于绘制按钮边框的形状。

- **ButtonRole**：描述按钮用途的值。

- **ButtonRepeatBehavior**：控制按钮操作重复性的选项。

- **ButtonSizing**：`Button` 和其他类似按钮的控件的大小调整行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/buttonBorderShape(_:)
crawled: 2025-11-30T21:21:03Z
---

# buttonBorderShape(_:)

**Instance Method**

Sets the border shape for buttons in this view.

## Declaration

```swift
nonisolated func buttonBorderShape(_ shape: ButtonBorderShape) -> some View

```

## Parameters

- **shape**: The shape to use.

## Discussion

The border shape is used to draw the platter for a bordered button.

The border shape affects buttons of the [bordered](../PrimitiveButtonStyle/bordered.zh-Hans.md) and [borderedProminent](../PrimitiveButtonStyle/borderedProminent.zh-Hans.md) styles.



## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

