---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/buttonRepeatBehavior
抓取时间：2025-12-02T17:36:00Z
---

# buttonRepeatBehavior

**实例属性**

具有此关联环境的按钮是否应在长时间交互时重复触发其动作。

## 声明

```swift
var buttonRepeatBehavior: ButtonRepeatBehavior { get }
```

## 讨论

`enabled`的值表示按钮可以重复触发其动作，`disabled`的值表示按钮不应该重复触发其动作。`automatic`的值表示按钮将遵从默认行为。

## 创建按钮

- **Button**：启动操作的控件。
- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。
- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。
- **buttonRepeatBehavior(_:)**：设置此视图中按钮的边框形状：设置该视图中的按钮是否应在长时间交互时重复触发其动作。
- **ButtonBorderShape**：用于绘制按钮边框的形状。
- **ButtonRole**：用于绘制按钮边框的形状：描述按钮用途的值。
- **ButtonRepeatBehavior**：用于控制按钮操作重复性的选项。
- **ButtonSizing**：`Button`和其他类似按钮控件的大小行为。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/buttonRepeatBehavior
crawled: 2025-12-02T17:36:00Z
---

# buttonRepeatBehavior

**Instance Property**

Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.

## Declaration

```swift
var buttonRepeatBehavior: ButtonRepeatBehavior { get }
```

## Discussion

A value of `enabled` means that buttons will be able to repeatedly trigger their action, and `disabled` means they should not. A value of `automatic` means that buttons will defer to default behavior.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

