---
来源： https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/automatic
抓取时间： 2025-12-02T21:50:18Z
---

# 自动

**类型属性**

基于按钮上下文的默认按钮样式。

## 声明

```swift
@MainActor @preconcurrency static var automatic: DefaultButtonStyle { get }
```

## 讨论

iOS 默认使用无边框按钮样式，而 macOS、tvOS 和 watchOS 则使用有边框按钮样式。

如果在容器（如[List](../List.zh-Hans.md)）内创建按钮，则样式会解析为该特定平台推荐的容器内按钮样式。

您可以覆盖按钮的样式。要将默认样式应用于按钮或包含按钮的视图，请使用[buttonStyle(_:)](../View/buttonStyle.zh-Hans.md)修饰符。

## 获取内置按钮样式

- **accessoryBar**：一种按钮样式，通常用于附件工具栏（有时称为 "范围栏"），用于缩小搜索或其他操作焦点的按钮。
- **accessoryBarAction**：附件工具栏中用于额外操作的按钮样式。
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
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/automatic
crawled: 2025-12-02T21:50:18Z
---

# automatic

**Type Property**

The default button style, based on the button’s context.

## Declaration

```swift
@MainActor @preconcurrency static var automatic: DefaultButtonStyle { get }
```

## Discussion

If you create a button directly on a blank canvas, the style varies by platform. iOS uses the borderless button style by default, whereas macOS, tvOS, and watchOS use the bordered button style.

If you create a button inside a container, like a [List](../List.zh-Hans.md), the style resolves to the recommended style for buttons inside that container for that specific platform.

You can override a button’s style. To apply the default style to a button, or to a view that contains buttons, use the [buttonStyle(_:)](../View/buttonStyle.zh-Hans.md) modifier.

## Getting built-in button styles

- **accessoryBar**: A button style that is typically used in the context of an accessory toolbar (sometimes refererred to as a “scope bar”), for buttons that narrow the focus of a search or other operation.
- **accessoryBarAction**: A button style that you use for extra actions in an accessory toolbar.
- **bordered**: A button style that applies the standard border style based on the button’s context.
- **borderedProminent**: A button style that applies the standard bordered prominent style based on the button’s context.
- **borderless**: A button style that doesn’t apply a border.
- **card**: A button style that doesn’t pad the content, and applies a Liquid Glass effect when the button has focus.
- **glass**: A button style that applies a Liquid Glass effect based on the button’s context.
- **glassProminent**: A button style that applies a prominent Liquid Glass effect based on the button’s context.
- **glass(_:)**: A button style that applies a configurable Liquid Glass effect based on the button’s context.
- **link**: A button style for buttons that emulate links.
- **plain**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

