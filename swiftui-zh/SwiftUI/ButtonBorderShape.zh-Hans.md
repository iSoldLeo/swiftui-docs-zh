---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonBorderShape
抓取时间： 2025-12-02T17:26:39Z
---

# 按钮边框形状

**Structure**

用于绘制按钮边框的形状。

## 声明

```swift
struct ButtonBorderShape
```

## 概览

使用[buttonBorderShape(_:)](View/buttonBorderShape.zh-Hans.md) 视图修改器可将形状应用于视图层次结构中的有边框按钮。

## 获取边框形状

- **automatic**：一种形状，由系统根据给定的上下文和平台确定合适的形状。
- **capsule**：胶囊形状。
- **circle**：圆形。
- **roundedRectangle**：圆形：圆角矩形。
- **roundedRectangle(radius:)**：圆形：圆角矩形。

## 创建按钮

- **Button**：启动操作的控件。
- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。
- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。
- **buttonRepeatBehavior(_:)**：设置该视图中按钮的边框形状：设置该视图中的按钮是否应在长时间交互时重复触发其动作。
- **buttonRepeatBehavior**：该关联环境中的按钮是否应在长时间交互时重复触发其操作。
- **ButtonRole**：描述按钮用途的值。
- **ButtonRepeatBehavior**：用于控制按钮操作重复性的选项。
- **ButtonSizing**：`Button`和其他类似按钮控件的大小行为。

## 符合

- 可动画
- 可复制
- 等价
- 可嵌入形状
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonBorderShape
crawled: 2025-12-02T17:26:39Z
---

# ButtonBorderShape

**Structure**

A shape used to draw a button’s border.

## Declaration

```swift
struct ButtonBorderShape
```

## Overview

Use the [buttonBorderShape(_:)](View/buttonBorderShape.zh-Hans.md) view modifier to apply the shape to bordered buttons within a view hierarchy.

## Getting border shapes

- **automatic**: A shape that defers to the system to determine an appropriate shape for the given context and platform.
- **capsule**: A capsule shape.
- **circle**: A circular shape.
- **roundedRectangle**: A rounded rectangle shape.
- **roundedRectangle(radius:)**: A rounded rectangle shape.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

## Conforms To

- Animatable
- Copyable
- Equatable
- InsettableShape
- Sendable
- SendableMetatype
- Shape
- View

