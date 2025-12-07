---

来源：https://developer.apple.com/documentation/SwiftUI/AccessoryBarActionButtonStyle
抓取时间：2025-12-03T06:09:07Z

---

# AccessoryBarActionButtonStyle

**Structure**

用于辅助工具栏中额外操作的按钮样式。

## 声明

```swift
struct AccessoryBarActionButtonStyle
```

## 概述

此样式用于执行与辅助工具栏主要功能相关的额外操作的按钮，例如添加或编辑筛选器。此样式还会影响您应用按钮样式的其他视图类型，例如 [Toggle](Toggle.zh-Hans.md)、[Picker](Picker.zh-Hans.md) 和 [Menu](Menu.zh-Hans.md) 实例。

使用 [accessoryBarAction](PrimitiveButtonStyle/accessoryBarAction.zh-Hans.md) 构造此样式。

## 创建按钮样式

- **init()**：创建辅助工具栏操作按钮样式

## 支持的类型

- **makeBody(configuration:)**：创建表示按钮主体的视图。

## 支持的类型

- **DefaultButtonStyle**：基于按钮上下文的默认按钮样式。

- **AccessoryBarButtonStyle**：用于辅助工具栏中缩小搜索或其他操作范围的操作的按钮样式。

- **BorderedButtonStyle**：根据按钮上下文应用标准边框样式的按钮样式。

- **BorderedProminentButtonStyle**：根据按钮上下文应用标准边框突出显示样式的按钮样式。

- **BorderlessButtonStyle**：不应用边框的按钮样式。

- **CardButtonStyle**：一种按钮样式，不会填充内容，并在按钮获得焦点时应用动态效果。

- **LinkButtonStyle**：一种用于模拟链接的按钮样式。

- **PlainButtonStyle**：一种按钮样式，在按钮处于空闲状态时不会对其内容进行样式设置或装饰，但可能会应用视觉效果来指示按钮的按下、聚焦或启用状态。

## 符合以下样式表：

- PrimitiveButtonStyle


---
source: https://developer.apple.com/documentation/SwiftUI/AccessoryBarActionButtonStyle
crawled: 2025-12-03T06:09:07Z
---

# AccessoryBarActionButtonStyle

**Structure**

A button style that you use for extra actions in an accessory toolbar.

## Declaration

```swift
struct AccessoryBarActionButtonStyle
```

## Overview

Use this style for buttons that perform extra actions relative to the accessory toolbar’s main functions, like adding or editing filters. This style also affects other view types that you apply a button style to, like [Toggle](Toggle.zh-Hans.md), [Picker](Picker.zh-Hans.md), and [Menu](Menu.zh-Hans.md) instances.

Use [accessoryBarAction](PrimitiveButtonStyle/accessoryBarAction.zh-Hans.md) to construct this style.

## Creating the button style

- **init()**: Creates an accessory toolbar action button style

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a button.

## Supporting types

- **DefaultButtonStyle**: The default button style, based on the button’s context.
- **AccessoryBarButtonStyle**: A button style that you use for actions in an accessory toolbar that narrow the focus of a search or other operation.
- **BorderedButtonStyle**: A button style that applies standard border artwork based on the button’s context.
- **BorderedProminentButtonStyle**: A button style that applies standard border prominent artwork based on the button’s context.
- **BorderlessButtonStyle**: A button style that doesn’t apply a border.
- **CardButtonStyle**: A button style that doesn’t pad the content, and applies a motion effect when a button has focus.
- **LinkButtonStyle**: A button style for buttons that emulate links.
- **PlainButtonStyle**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

## Conforms To

- PrimitiveButtonStyle

