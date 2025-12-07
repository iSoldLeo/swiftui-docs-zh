--- 来源：https://developer.apple.com/documentation/SwiftUI/DefaultButtonStyle
抓取时间：2025-12-03T06:09:06Z

---

# DefaultButtonStyle

**Structure**

基于按钮上下文的默认按钮样式。

## 声明

```swift
struct DefaultButtonStyle
```

## 概述

您也可以使用 [automatic](PrimitiveButtonStyle/automatic.zh-Hans.md) 来构造此样式。

## 创建按钮样式

- **init()**：创建默认按钮样式。

## 支持的类型

- **makeBody(configuration:)**：创建表示按钮主体的视图。

## 支持的类型

- **AccessoryBarButtonStyle**：用于辅助工具栏中缩小搜索或其他操作焦点的按钮样式。

- **AccessoryBarActionButtonStyle**：用于辅助工具栏中额外操作的按钮样式。

- **BorderedButtonStyle**：根据按钮上下文应用标准边框样式的按钮样式。

- **BorderedProminentButtonStyle**：根据按钮上下文应用标准边框突出显示样式的按钮样式。

- **BorderlessButtonStyle**：不应用边框的按钮样式。

- **CardButtonStyle**：不添加内容内边距的按钮样式，并在按钮获得焦点时应用动态效果。

- **LinkButtonStyle**：用于模拟链接的按钮样式。

- **PlainButtonStyle**：一种按钮样式，在按钮处于空闲状态时不会对其内容进行样式或装饰，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。

## 符合以下样式表：

- PrimitiveButtonStyle


---
source: https://developer.apple.com/documentation/SwiftUI/DefaultButtonStyle
crawled: 2025-12-03T06:09:06Z
---

# DefaultButtonStyle

**Structure**

The default button style, based on the button’s context.

## Declaration

```swift
struct DefaultButtonStyle
```

## Overview

You can also use [automatic](PrimitiveButtonStyle/automatic.zh-Hans.md) to construct this style.

## Creating the button style

- **init()**: Creates a default button style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a button.

## Supporting types

- **AccessoryBarButtonStyle**: A button style that you use for actions in an accessory toolbar that narrow the focus of a search or other operation.
- **AccessoryBarActionButtonStyle**: A button style that you use for extra actions in an accessory toolbar.
- **BorderedButtonStyle**: A button style that applies standard border artwork based on the button’s context.
- **BorderedProminentButtonStyle**: A button style that applies standard border prominent artwork based on the button’s context.
- **BorderlessButtonStyle**: A button style that doesn’t apply a border.
- **CardButtonStyle**: A button style that doesn’t pad the content, and applies a motion effect when a button has focus.
- **LinkButtonStyle**: A button style for buttons that emulate links.
- **PlainButtonStyle**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

## Conforms To

- PrimitiveButtonStyle

