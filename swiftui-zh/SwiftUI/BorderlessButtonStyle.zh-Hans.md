---
来源： https://developer.apple.com/documentation/SwiftUI/BorderlessButtonStyle
抓取时间： 2025-12-03T06:09:10Z
---

# 无边框按钮样式

**Structure**

不应用边框的按钮样式。

## 声明

```swift
struct BorderlessButtonStyle
```

## 概览

您也可以使用 [borderless](PrimitiveButtonStyle/borderless.zh-Hans.md) 构建这种样式。

## 创建按钮样式

- **init()**：创建无边框按钮样式。

## 支持类型

- **makeBody(configuration:)**：创建表示按钮主体的视图。

## 支持类型

- **DefaultButtonStyle**：基于按钮上下文的默认按钮样式。
- **AccessoryBarButtonStyle**：用于附件工具栏中缩小搜索或其他操作焦点的操作的按钮样式。
- **AccessoryBarActionButtonStyle**：用于附件工具栏中额外操作的按钮样式。
- **BorderedButtonStyle**：根据按钮上下文应用标准边框图案的按钮样式。
- **BorderedProminentButtonStyle**：根据按钮上下文应用标准边框突出图案的按钮样式。
- **CardButtonStyle**：一种按钮样式，不填充内容，并在按钮有焦点时应用动态效果。
- **LinkButtonStyle**：用于模拟链接的按钮样式。
- **PlainButtonStyle**：一种按钮样式，在空闲时不会样式化或装饰其内容，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。

## 符合

- 原始按钮样式


---
source: https://developer.apple.com/documentation/SwiftUI/BorderlessButtonStyle
crawled: 2025-12-03T06:09:10Z
---

# BorderlessButtonStyle

**Structure**

A button style that doesn’t apply a border.

## Declaration

```swift
struct BorderlessButtonStyle
```

## Overview

You can also use [borderless](PrimitiveButtonStyle/borderless.zh-Hans.md) to construct this style.

## Creating the button style

- **init()**: Creates a borderless button style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a button.

## Supporting types

- **DefaultButtonStyle**: The default button style, based on the button’s context.
- **AccessoryBarButtonStyle**: A button style that you use for actions in an accessory toolbar that narrow the focus of a search or other operation.
- **AccessoryBarActionButtonStyle**: A button style that you use for extra actions in an accessory toolbar.
- **BorderedButtonStyle**: A button style that applies standard border artwork based on the button’s context.
- **BorderedProminentButtonStyle**: A button style that applies standard border prominent artwork based on the button’s context.
- **CardButtonStyle**: A button style that doesn’t pad the content, and applies a motion effect when a button has focus.
- **LinkButtonStyle**: A button style for buttons that emulate links.
- **PlainButtonStyle**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

## Conforms To

- PrimitiveButtonStyle

