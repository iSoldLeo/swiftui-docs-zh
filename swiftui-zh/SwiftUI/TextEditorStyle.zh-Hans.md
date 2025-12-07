---
来源： https://developer.apple.com/documentation/SwiftUI/TextEditorStyle
抓取时间： 2025-12-02T17:33:19Z
---

# TextEditorStyle

**Protocol**

文本编辑器的外观和交互规范。

## 声明

```swift
@MainActor @preconcurrency protocol TextEditorStyle
```

## 概览

如果符合本协议的类型的基本声明中包含了本协议，那么该类型就继承了本协议的 `@preconcurrency @MainActor` 隔离性：

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

## 获取内置样式

- **automatic**：基于文本编辑器上下文的默认文本编辑器样式。
- **plain**：无装饰的文本编辑器样式。
- **roundedBorder**：带有系统定义的圆形边框的文本编辑器样式。

## 创建自定义样式

- **makeBody(configuration:)**：创建表示文本编辑器主体的视图。
- **TextEditorStyle.Configuration**：文本编辑器的属性。
- **Body**：文本编辑器的属性：表示文本编辑器主体的视图。

## 支持类型

- **AutomaticTextEditorStyle**：基于文本编辑器上下文的默认文本编辑器样式。
- **PlainTextEditorStyle**：无装饰的文本编辑器样式。
- **RoundedBorderTextEditorStyle**：带有系统定义的圆形边框的文本编辑器样式。

## 显示文本的视图样式

- **labelStyle(_:)**：为该视图中的标签设置样式。
- **LabelStyle**：为视图中的所有标签应用自定义外观的类型。
- **LabelStyleConfiguration**：标签的属性。
- **textFieldStyle(_:)**：标签的属性：设置该视图中文本字段的样式。
- **TextFieldStyle**：文本字段的外观和交互规范。
- **textEditorStyle(_:)**：设置该视图中文本编辑器的样式。
- **TextEditorStyleConfiguration**：文本编辑器的属性。

## 符合类型

- 自动文本编辑器样式
- 普通文本编辑器样式
- 圆形边框文本编辑器样式


---
source: https://developer.apple.com/documentation/SwiftUI/TextEditorStyle
crawled: 2025-12-02T17:33:19Z
---

# TextEditorStyle

**Protocol**

A specification for the appearance and interaction of a text editor.

## Declaration

```swift
@MainActor @preconcurrency protocol TextEditorStyle
```

## Overview

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

## Getting built-in styles

- **automatic**: The default text editor style, based on the text editor’s context.
- **plain**: A text editor style with no decoration.
- **roundedBorder**: A text editor style with a system-defined rounded border.

## Creating custom styles

- **makeBody(configuration:)**: Creates a view that represents the body of a text editor.
- **TextEditorStyle.Configuration**: The properties of a text editor.
- **Body**: A view that represents the body of a text editor.

## Supporting types

- **AutomaticTextEditorStyle**: The default text editor style, based on the text editor’s context.
- **PlainTextEditorStyle**: A text editor style with no decoration.
- **RoundedBorderTextEditorStyle**: A text editor style with a system-defined rounded border.

## Styling views that display text

- **labelStyle(_:)**: Sets the style for labels within this view.
- **LabelStyle**: A type that applies a custom appearance to all labels within a view.
- **LabelStyleConfiguration**: The properties of a label.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **TextFieldStyle**: A specification for the appearance and interaction of a text field.
- **textEditorStyle(_:)**: Sets the style for text editors within this view.
- **TextEditorStyleConfiguration**: The properties of a text editor.

## Conforming Types

- AutomaticTextEditorStyle
- PlainTextEditorStyle
- RoundedBorderTextEditorStyle

