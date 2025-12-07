--- 来源：https://developer.apple.com/documentation/SwiftUI/ButtonRole
抓取时间：2025-12-02T17:36:01Z

---

# ButtonRole

**Structure**

描述按钮用途的值。

## 声明

```swift
struct ButtonRole
```

## 概述

按钮角色描述了按钮的用途。例如，[destructive](ButtonRole/destructive.zh-Hans.md) 角色表示按钮执行破坏性操作，例如删除用户数据：

```swift
Button("Delete", role: .destructive) { delete() }
```

## 获取按钮角色

- **cancel**：表示取消操作的按钮的角色。

- **destructive**：表示执行破坏性操作的按钮的角色。

## 类型属性

- **close**：用于指示关闭当前操作的按钮的角色。

- **confirm**：用于指示确认操作的按钮的角色。

## 创建按钮

- **Button**：用于启动操作的控件。

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。

- **buttonRepeatBehavior(_:)**：设置此视图中的按钮在长时间交互后是否应重复触发其操作。

- **buttonRepeatBehavior**：设置具有此关联环境的按钮在长时间交互后是否应重复触发其操作。

- **ButtonBorderShape**：用于绘制按钮边框的形状。

- **ButtonRepeatBehavior**：用于控制按钮操作重复性的选项。

- **ButtonSizing**：`Button` 和其他类似按钮的控件的大小调整行为。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonRole
crawled: 2025-12-02T17:36:01Z
---

# ButtonRole

**Structure**

A value that describes the purpose of a button.

## Declaration

```swift
struct ButtonRole
```

## Overview

A button role provides a description of a button’s purpose.  For example, the [destructive](ButtonRole/destructive.zh-Hans.md) role indicates that a button performs a destructive action, like delete user data:

```swift
Button("Delete", role: .destructive) { delete() }
```

## Getting button roles

- **cancel**: A role that indicates a button that cancels an operation.
- **destructive**: A role that indicates a destructive button.

## Type Properties

- **close**: A role that indicates a button that closes the current operation.
- **confirm**: A role that indicates a button that confirms an operation.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

