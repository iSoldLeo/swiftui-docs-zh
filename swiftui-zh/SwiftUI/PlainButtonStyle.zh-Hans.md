--- 来源：https://developer.apple.com/documentation/SwiftUI/PlainButtonStyle
抓取时间：2025-12-03T06:09:12Z

---

# PlainButtonStyle

**Structure**

此按钮样式在按钮处于空闲状态时不会对其内容进行样式设置或装饰，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。

## 声明

```swift
struct PlainButtonStyle
```

## 概述

您也可以使用 [plain](PrimitiveButtonStyle/plain.zh-Hans.md) 来构建此样式。

## 创建按钮样式

- **init()**：创建一个纯按钮样式。

## 支持的类型

- **makeBody(configuration:)**：创建一个表示按钮主体的视图。

## 支持的类型

- **DefaultButtonStyle**：默认按钮样式，基于按钮的上下文。

- **AccessoryBarButtonStyle**：用于辅助工具栏中缩小搜索或其他操作焦点的按钮样式。

- **AccessoryBarActionButtonStyle**：用于辅助工具栏中额外操作的按钮样式。

- **BorderedButtonStyle**：根据按钮的上下文应用标准边框的按钮样式。

- **BorderedProminentButtonStyle**：根据按钮的上下文应用标准边框突出显示的按钮样式。

- **BorderlessButtonStyle**：不应用边框的按钮样式。

- **CardButtonStyle**：不添加内边距的按钮样式，并在按钮获得焦点时应用动态效果。

- **LinkButtonStyle**：一种模拟链接的按钮样式。

## 符合以下样式：

- PrimitiveButtonStyle


---
source: https://developer.apple.com/documentation/SwiftUI/PlainButtonStyle
crawled: 2025-12-03T06:09:12Z
---

# PlainButtonStyle

**Structure**

A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

## Declaration

```swift
struct PlainButtonStyle
```

## Overview

You can also use [plain](PrimitiveButtonStyle/plain.zh-Hans.md) to construct this style.

## Creating the button style

- **init()**: Creates a plain button style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a button.

## Supporting types

- **DefaultButtonStyle**: The default button style, based on the button’s context.
- **AccessoryBarButtonStyle**: A button style that you use for actions in an accessory toolbar that narrow the focus of a search or other operation.
- **AccessoryBarActionButtonStyle**: A button style that you use for extra actions in an accessory toolbar.
- **BorderedButtonStyle**: A button style that applies standard border artwork based on the button’s context.
- **BorderedProminentButtonStyle**: A button style that applies standard border prominent artwork based on the button’s context.
- **BorderlessButtonStyle**: A button style that doesn’t apply a border.
- **CardButtonStyle**: A button style that doesn’t pad the content, and applies a motion effect when a button has focus.
- **LinkButtonStyle**: A button style for buttons that emulate links.

## Conforms To

- PrimitiveButtonStyle

