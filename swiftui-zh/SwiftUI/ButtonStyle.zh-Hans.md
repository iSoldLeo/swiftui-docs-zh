---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonStyle
抓取时间： 2025-12-02T17:33:01Z
---

# 按钮样式

**Protocol**

将标准交互行为和自定义外观应用于视图层次结构中所有按钮的类型。

### 声明

```swift
@MainActor @preconcurrency protocol ButtonStyle
```

## 概览

要为视图层次结构配置当前按钮样式，请使用 [buttonStyle(_:)](View/buttonStyle.zh-Hans.md) 修改器。在创建使用为每个平台定义的标准按钮交互行为的按钮时，请指定符合 `ButtonStyle` 的样式。要创建具有自定义交互行为的按钮，请使用 [PrimitiveButtonStyle](PrimitiveButtonStyle.zh-Hans.md)。

## 自定义按钮样式

- **makeBody(configuration:)**：创建表示按钮主体的视图。
- **ButtonStyle.Configuration**：按钮的属性。
- **Body**：表示按钮主体的视图。

## 按钮样式

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。
- **ButtonStyleConfiguration**：按钮的属性。
- **PrimitiveButtonStyle**：按钮的属性：将自定义交互行为和自定义外观应用于视图层次结构中所有按钮的类型。
- **PrimitiveButtonStyleConfiguration**：按钮的属性。
- **signInWithAppleButtonStyle(_:)**：按钮的属性：设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonStyle
crawled: 2025-12-02T17:33:01Z
---

# ButtonStyle

**Protocol**

A type that applies standard interaction behavior and a custom appearance to all buttons within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol ButtonStyle
```

## Overview

To configure the current button style for a view hierarchy, use the [buttonStyle(_:)](View/buttonStyle.zh-Hans.md) modifier. Specify a style that conforms to `ButtonStyle` when creating a button that uses the standard button interaction behavior defined for each platform. To create a button with custom interaction behavior, use [PrimitiveButtonStyle](PrimitiveButtonStyle.zh-Hans.md) instead.

## Custom button styles

- **makeBody(configuration:)**: Creates a view that represents the body of a button.
- **ButtonStyle.Configuration**: The properties of a button.
- **Body**: A view that represents the body of a button.

## Styling buttons

- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **ButtonStyleConfiguration**: The properties of a button.
- **PrimitiveButtonStyle**: A type that applies custom interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **PrimitiveButtonStyleConfiguration**: The properties of a button.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).

