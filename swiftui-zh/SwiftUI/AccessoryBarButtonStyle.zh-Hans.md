---
来源： https://developer.apple.com/documentation/SwiftUI/AccessoryBarButtonStyle
抓取时间：2025-12-03T06:09:07Z
---

# 附件栏按钮样式

**Structure**

一种按钮样式，用于附件工具栏中缩小搜索或其他操作焦点的操作。

## 声明

```swift
struct AccessoryBarButtonStyle
```

## 概览

这是附件工具栏中视图和可搜索作用域的默认按钮样式，您可以使用[init(id:)](ToolbarItemPlacement/init_id.zh-Hans.md) 创建附件工具栏和可搜索作用域。此样式也会影响应用了按钮样式的其他视图类型，如[Toggle](Toggle.zh-Hans.md)、[Picker](Picker.zh-Hans.md) 和[Menu](Menu.zh-Hans.md) 实例。

使用 [accessoryBar](PrimitiveButtonStyle/accessoryBar.zh-Hans.md) 构建这种样式。

## 创建按钮样式

- **init()**：创建附件工具栏样式

## 支持类型

- **makeBody(configuration:)**：创建表示按钮主体的视图。

## 支持类型

- **DefaultButtonStyle**：基于按钮上下文的默认按钮样式。
- **AccessoryBarActionButtonStyle**：用于附件工具栏中额外操作的按钮样式。
- **BorderedButtonStyle**：根据按钮上下文应用标准边框图案的按钮样式。
- **BorderedProminentButtonStyle**：根据按钮上下文应用标准边框突出图案的按钮样式。
- **BorderlessButtonStyle**：不应用边框的按钮样式。
- **CardButtonStyle**：不应用边框的按钮样式：不填充内容的按钮样式，当按钮有焦点时会应用动态效果。
- **LinkButtonStyle**：用于模拟链接的按钮样式。
- **PlainButtonStyle**：一种按钮样式，在空闲时不会样式化或装饰其内容，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。

## 符合

- 原始按钮样式


---
source: https://developer.apple.com/documentation/SwiftUI/AccessoryBarButtonStyle
crawled: 2025-12-03T06:09:07Z
---

# AccessoryBarButtonStyle

**Structure**

A button style that you use for actions in an accessory toolbar that narrow the focus of a search or other operation.

## Declaration

```swift
struct AccessoryBarButtonStyle
```

## Overview

This is the default button style for views in accessory toolbars, which you create with [init(id:)](ToolbarItemPlacement/init_id.zh-Hans.md), and for searchable scopes. This style also affects other view types that you apply a button style to, like [Toggle](Toggle.zh-Hans.md), [Picker](Picker.zh-Hans.md), and [Menu](Menu.zh-Hans.md) instances.

Use [accessoryBar](PrimitiveButtonStyle/accessoryBar.zh-Hans.md) to construct this style.

## Creating the button style

- **init()**: Creates an accessory toolbar style

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a button.

## Supporting types

- **DefaultButtonStyle**: The default button style, based on the button’s context.
- **AccessoryBarActionButtonStyle**: A button style that you use for extra actions in an accessory toolbar.
- **BorderedButtonStyle**: A button style that applies standard border artwork based on the button’s context.
- **BorderedProminentButtonStyle**: A button style that applies standard border prominent artwork based on the button’s context.
- **BorderlessButtonStyle**: A button style that doesn’t apply a border.
- **CardButtonStyle**: A button style that doesn’t pad the content, and applies a motion effect when a button has focus.
- **LinkButtonStyle**: A button style for buttons that emulate links.
- **PlainButtonStyle**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

## Conforms To

- PrimitiveButtonStyle

