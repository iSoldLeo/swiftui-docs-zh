---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonRepeatBehavior
抓取时间： 2025-12-02T17:36:02Z
---

# ButtonRepeatBehavior

**Structure**

用于控制按钮操作重复性的选项。

## 声明

```swift
struct ButtonRepeatBehavior
```

## 概览

使用该类型的值时，应同时使用[buttonRepeatBehavior(_:)](View/buttonRepeatBehavior.zh-Hans.md)修饰符。

## 获取重复行为

- **automatic**：自动重复行为。
- **enabled**：将启用重复按钮操作。
- **disabled**： 启用重复按钮操作：将禁用重复按钮操作。

## 创建按钮

- **Button**：启动操作的控件。
- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。
- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。
- **buttonRepeatBehavior(_:)**：设置该视图中按钮的边框形状：设置该视图中的按钮是否应在长时间交互时重复触发其动作。
- **buttonRepeatBehavior**：该关联环境中的按钮是否应在长时间交互时重复触发其操作。
- **ButtonBorderShape**：用于绘制按钮边框的形状。
- **ButtonRole**：描述按钮用途的值。
- **ButtonSizing**：`Button`和其他类似按钮控件的大小行为。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonRepeatBehavior
crawled: 2025-12-02T17:36:02Z
---

# ButtonRepeatBehavior

**Structure**

The options for controlling the repeatability of button actions.

## Declaration

```swift
struct ButtonRepeatBehavior
```

## Overview

Use values of this type with the [buttonRepeatBehavior(_:)](View/buttonRepeatBehavior.zh-Hans.md) modifier.

## Getting repeat behaviors

- **automatic**: The automatic repeat behavior.
- **enabled**: Repeating button actions will be enabled.
- **disabled**: Repeating button actions will be disabled.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

