---
来源： https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/glassProminent
抓取时间： 2025-12-02T21:50:23Z
---

# 玻璃突出

**类型属性**

一种按钮样式，可根据按钮的上下文应用突出的液态玻璃效果。

## 声明

```swift
@MainActor @preconcurrency static var glassProminent: GlassProminentButtonStyle { get }
```

## 讨论

在 tvOS 中，无论按钮是否处于焦点位置，该按钮样式都会应用液态玻璃效果。该样式类似于 [borderedProminent](borderedProminent.zh-Hans.md) 样式。

要将此样式应用于按钮或包含按钮的视图，请使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/View/buttonStyle(_:)-66fbx] 修改器。

## 获取内置按钮样式

- **automatic**：基于按钮上下文的默认按钮样式。
- **accessoryBar**：通常在附件工具栏（有时称为 "范围栏"）中使用的按钮样式，用于缩小搜索或其他操作焦点的按钮。
- **accessoryBarAction**：附件工具栏中用于额外操作的按钮样式。
- **bordered**：根据按钮上下文应用标准边框样式的按钮样式。
- **borderedProminent**：根据按钮上下文应用标准边框突出样式的按钮样式。
- **borderless**：不应用边框的按钮样式。
- **card**：不应用边框的按钮样式：不填充内容的按钮样式，当按钮有焦点时会应用液态玻璃效果。
- **glass**：根据按钮上下文应用 Liquid Glass 效果的按钮样式。
- **glass(_:)**：一种按钮样式，可根据按钮的上下文应用可配置的 Liquid Glass 效果。
- **link**：用于模拟链接的按钮样式。
- **plain**：一种按钮样式，在空闲时不会样式化或装饰其内容，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。


---
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/glassProminent
crawled: 2025-12-02T21:50:23Z
---

# glassProminent

**Type Property**

A button style that applies a prominent Liquid Glass effect based on the button’s context.

## Declaration

```swift
@MainActor @preconcurrency static var glassProminent: GlassProminentButtonStyle { get }
```

## Discussion

In tvOS, this button style applies a Liquid Glass effect regardless of whether the button has focus. This style is similar to the [borderedProminent](borderedProminent.zh-Hans.md) style.

To apply this style to a button, or to a view that contains buttons, use the [doc://com.apple.SwiftUI/documentation/SwiftUI/View/buttonStyle(_:)-66fbx] modifier.

## Getting built-in button styles

- **automatic**: The default button style, based on the button’s context.
- **accessoryBar**: A button style that is typically used in the context of an accessory toolbar (sometimes refererred to as a “scope bar”), for buttons that narrow the focus of a search or other operation.
- **accessoryBarAction**: A button style that you use for extra actions in an accessory toolbar.
- **bordered**: A button style that applies the standard border style based on the button’s context.
- **borderedProminent**: A button style that applies the standard bordered prominent style based on the button’s context.
- **borderless**: A button style that doesn’t apply a border.
- **card**: A button style that doesn’t pad the content, and applies a Liquid Glass effect when the button has focus.
- **glass**: A button style that applies a Liquid Glass effect based on the button’s context.
- **glass(_:)**: A button style that applies a configurable Liquid Glass effect based on the button’s context.
- **link**: A button style for buttons that emulate links.
- **plain**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

