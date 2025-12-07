---
来源： https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/accessoryBarAction
抓取时间： 2025-12-02T21:50:20Z
---

# 配件栏动作

**类型属性**

用于附件工具栏中额外操作的按钮样式。

## 声明

```swift
@MainActor @preconcurrency static var accessoryBarAction: AccessoryBarActionButtonStyle { get }
```

## 讨论

该样式适用于执行附件工具栏主要功能之外的额外操作的按钮，如添加或编辑过滤器。此样式也会影响应用了按钮样式的其他视图类型，如 [Toggle](../Toggle.zh-Hans.md)、[Picker](../Picker.zh-Hans.md) 和 [Menu](../Menu.zh-Hans.md) 实例。

## 获取内置按钮样式

- **automatic**：基于按钮上下文的默认按钮样式。
- **accessoryBar**：通常在附件工具栏（有时称为 "范围栏"）中使用的按钮样式，用于缩小搜索或其他操作焦点的按钮。
- **bordered**：根据按钮上下文应用标准边框样式的按钮样式。
- **borderedProminent**：根据按钮上下文应用标准边框突出样式的按钮样式。
- **borderless**：不应用边框的按钮样式。
- **card**：不应用边框的按钮样式：不填充内容的按钮样式，当按钮有焦点时会应用液态玻璃效果。
- **glass**：根据按钮上下文应用 Liquid Glass 效果的按钮样式。
- **glassProminent**：一种按钮样式，可根据按钮的上下文应用突出的 Liquid Glass 效果。
- **glass(_:)**：根据按钮上下文应用可配置 Liquid Glass 效果的按钮样式。
- **link**：用于模拟链接的按钮样式。
- **plain**：一种按钮样式，在空闲时不会样式化或装饰其内容，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。


---
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/accessoryBarAction
crawled: 2025-12-02T21:50:20Z
---

# accessoryBarAction

**Type Property**

A button style that you use for extra actions in an accessory toolbar.

## Declaration

```swift
@MainActor @preconcurrency static var accessoryBarAction: AccessoryBarActionButtonStyle { get }
```

## Discussion

Use this style for buttons that perform extra actions relative to the accessory toolbar’s main functions, like adding or editing filters. This style also affects other view types that you apply a button style to, like [Toggle](../Toggle.zh-Hans.md), [Picker](../Picker.zh-Hans.md), and [Menu](../Menu.zh-Hans.md) instances.

## Getting built-in button styles

- **automatic**: The default button style, based on the button’s context.
- **accessoryBar**: A button style that is typically used in the context of an accessory toolbar (sometimes refererred to as a “scope bar”), for buttons that narrow the focus of a search or other operation.
- **bordered**: A button style that applies the standard border style based on the button’s context.
- **borderedProminent**: A button style that applies the standard bordered prominent style based on the button’s context.
- **borderless**: A button style that doesn’t apply a border.
- **card**: A button style that doesn’t pad the content, and applies a Liquid Glass effect when the button has focus.
- **glass**: A button style that applies a Liquid Glass effect based on the button’s context.
- **glassProminent**: A button style that applies a prominent Liquid Glass effect based on the button’s context.
- **glass(_:)**: A button style that applies a configurable Liquid Glass effect based on the button’s context.
- **link**: A button style for buttons that emulate links.
- **plain**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

