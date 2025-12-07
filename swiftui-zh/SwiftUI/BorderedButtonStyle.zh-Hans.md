---
来源： https://developer.apple.com/documentation/SwiftUI/BorderedButtonStyle
抓取时间： 2025-12-03T06:09:09Z
---

# 边框按钮样式

**Structure**

根据按钮的上下文应用标准边框图案的按钮样式。

## 声明

```swift
struct BorderedButtonStyle
```

## 概览

您也可以使用 [bordered](PrimitiveButtonStyle/bordered.zh-Hans.md) 构建这种样式。

## 创建按钮样式

- **init()**：创建有边框的按钮样式。

## 支持类型

- **makeBody(configuration:)**：创建表示按钮主体的视图。

## 过时的符号

- **init(tint:)**：创建带颜色边框的按钮样式。

## 支持类型

- **DefaultButtonStyle**：默认按钮样式，基于按钮的上下文。
- **AccessoryBarButtonStyle**：用于附件工具栏中缩小搜索或其他操作焦点的操作的按钮样式。
- **AccessoryBarActionButtonStyle**：用于附件工具栏中额外操作的按钮样式。
- **BorderedProminentButtonStyle**：根据按钮上下文应用标准边框突出图案的按钮样式。
- **BorderlessButtonStyle**：不应用边框的按钮样式。
- **CardButtonStyle**：不应用边框的按钮样式：不填充内容的按钮样式，当按钮有焦点时会应用动态效果。
- **LinkButtonStyle**：用于模拟链接的按钮样式。
- **PlainButtonStyle**：一种按钮样式，在空闲时不会样式化或装饰其内容，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。

## 符合

- 原始按钮样式


---
source: https://developer.apple.com/documentation/SwiftUI/BorderedButtonStyle
crawled: 2025-12-03T06:09:09Z
---

# BorderedButtonStyle

**Structure**

A button style that applies standard border artwork based on the button’s context.

## Declaration

```swift
struct BorderedButtonStyle
```

## Overview

You can also use [bordered](PrimitiveButtonStyle/bordered.zh-Hans.md) to construct this style.

## Creating the button style

- **init()**: Creates a bordered button style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a button.

## Deprecated symbols

- **init(tint:)**: Creates a bordered button style with a tint color.

## Supporting types

- **DefaultButtonStyle**: The default button style, based on the button’s context.
- **AccessoryBarButtonStyle**: A button style that you use for actions in an accessory toolbar that narrow the focus of a search or other operation.
- **AccessoryBarActionButtonStyle**: A button style that you use for extra actions in an accessory toolbar.
- **BorderedProminentButtonStyle**: A button style that applies standard border prominent artwork based on the button’s context.
- **BorderlessButtonStyle**: A button style that doesn’t apply a border.
- **CardButtonStyle**: A button style that doesn’t pad the content, and applies a motion effect when a button has focus.
- **LinkButtonStyle**: A button style for buttons that emulate links.
- **PlainButtonStyle**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

## Conforms To

- PrimitiveButtonStyle

