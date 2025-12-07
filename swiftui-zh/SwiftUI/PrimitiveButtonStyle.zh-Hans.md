---
来源： https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle
抓取时间： 2025-12-02T17:33:03Z
---

# 原始按钮样式

**Protocol**

将自定义交互行为和自定义外观应用于视图层次结构中所有按钮的类型。

### 声明

```swift
@MainActor @preconcurrency protocol PrimitiveButtonStyle
```

## 概览

要为视图层次结构配置当前按钮样式，请使用 [buttonStyle(_:)](View/buttonStyle.zh-Hans.md) 修改器。指定符合`PrimitiveButtonStyle` 的样式可创建具有自定义交互行为的按钮。要创建具有为每个平台定义的标准按钮交互行为的按钮，请使用 [ButtonStyle](ButtonStyle.zh-Hans.md)。

如果符合该协议的类型的基本声明中包含该协议，则该类型将继承`@preconcurrency @MainActor` 隔离协议：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置按钮样式

- **automatic**：基于按钮上下文的默认按钮样式。
- **accessoryBar**：通常在附件工具栏（有时称为 "范围栏"）中使用的按钮样式，用于缩小搜索或其他操作焦点的按钮。
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

## 创建自定义按钮样式

- **makeBody(configuration:)**：创建表示按钮主体的视图。
- **PrimitiveButtonStyle.Configuration**：按钮的属性。
- **Body**：表示按钮主体的视图。

## 支持类型

- **DefaultButtonStyle**：基于按钮上下文的默认按钮样式。
- **AccessoryBarButtonStyle**：用于附件工具栏中缩小搜索或其他操作焦点的操作的按钮样式。
- **AccessoryBarActionButtonStyle**：用于附件工具栏中额外操作的按钮样式。
- **BorderedButtonStyle**：根据按钮上下文应用标准边框图案的按钮样式。
- **BorderedProminentButtonStyle**：根据按钮上下文应用标准边框突出图案的按钮样式。
- **BorderlessButtonStyle**：不应用边框的按钮样式。
- **CardButtonStyle**：不应用边框的按钮样式：不填充内容的按钮样式，当按钮有焦点时会应用动态效果。
- **LinkButtonStyle**：用于模拟链接的按钮样式。
- **PlainButtonStyle**：一种按钮样式，在空闲时不会样式化或装饰其内容，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。

## 按钮样式

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。
- **ButtonStyle**：将标准交互行为和自定义外观应用于视图层次结构中所有按钮的类型。
- **ButtonStyleConfiguration**：按钮的属性。
- **PrimitiveButtonStyleConfiguration**：按钮的属性：按钮的属性。
- **signInWithAppleButtonStyle(_:)**：按钮的属性：设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。

## 符合类型

- AccessoryBarActionButtonStyle
- 附件栏按钮样式
- 有边框按钮样式
- 有边框突出按钮样式
- 无边框按钮样式
- 卡片按钮样式
- 默认按钮样式
- 玻璃按钮样式
- 玻璃突出按钮样式
- 链接按钮样式
- 普通按钮样式


---
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle
crawled: 2025-12-02T17:33:03Z
---

# PrimitiveButtonStyle

**Protocol**

A type that applies custom interaction behavior and a custom appearance to all buttons within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol PrimitiveButtonStyle
```

## Overview

To configure the current button style for a view hierarchy, use the [buttonStyle(_:)](View/buttonStyle.zh-Hans.md) modifier. Specify a style that conforms to `PrimitiveButtonStyle` to create a button with custom interaction behavior. To create a button with the standard button interaction behavior defined for each platform, use [ButtonStyle](ButtonStyle.zh-Hans.md) instead.

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting built-in button styles

- **automatic**: The default button style, based on the button’s context.
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

## Creating custom button styles

- **makeBody(configuration:)**: Creates a view that represents the body of a button.
- **PrimitiveButtonStyle.Configuration**: The properties of a button.
- **Body**: A view that represents the body of a button.

## Supporting types

- **DefaultButtonStyle**: The default button style, based on the button’s context.
- **AccessoryBarButtonStyle**: A button style that you use for actions in an accessory toolbar that narrow the focus of a search or other operation.
- **AccessoryBarActionButtonStyle**: A button style that you use for extra actions in an accessory toolbar.
- **BorderedButtonStyle**: A button style that applies standard border artwork based on the button’s context.
- **BorderedProminentButtonStyle**: A button style that applies standard border prominent artwork based on the button’s context.
- **BorderlessButtonStyle**: A button style that doesn’t apply a border.
- **CardButtonStyle**: A button style that doesn’t pad the content, and applies a motion effect when a button has focus.
- **LinkButtonStyle**: A button style for buttons that emulate links.
- **PlainButtonStyle**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

## Styling buttons

- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **ButtonStyle**: A type that applies standard interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **ButtonStyleConfiguration**: The properties of a button.
- **PrimitiveButtonStyleConfiguration**: The properties of a button.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).

## Conforming Types

- AccessoryBarActionButtonStyle
- AccessoryBarButtonStyle
- BorderedButtonStyle
- BorderedProminentButtonStyle
- BorderlessButtonStyle
- CardButtonStyle
- DefaultButtonStyle
- GlassButtonStyle
- GlassProminentButtonStyle
- LinkButtonStyle
- PlainButtonStyle

