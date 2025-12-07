---
来源： https://developer.apple.com/documentation/SwiftUI/TextFieldStyle
抓取时间： 2025-12-02T17:33:17Z
---

# 文本字段样式

**Protocol**

文本字段的外观和交互规范。

## 声明

```swift
protocol TextFieldStyle
```

## 获取内置文本字段样式

- **automatic**：基于文本字段上下文的默认文本字段样式。
- **plain**：无装饰的文本字段样式。
- **roundedBorder**：无装饰的文本字段样式：带有系统定义的圆形边框的文本字段样式。
- **squareBorder**：带有系统定义的方形边框的文本字段样式。

### 支持类型

- **DefaultTextFieldStyle**：基于文本字段上下文的默认文本字段样式。
- **PlainTextFieldStyle**：无装饰的文本字段样式。
- **RoundedBorderTextFieldStyle**：带有系统定义的圆形边框的文本字段样式。
- **SquareBorderTextFieldStyle**：带有系统定义的方形边框的文本字段样式。

## 显示文本的视图样式

- **labelStyle(_:)**：设置该视图中标签的样式。
- **LabelStyle**：为视图中的所有标签应用自定义外观的类型。
- **LabelStyleConfiguration**：标签的属性。
- **textFieldStyle(_:)**：标签的属性：设置该视图中文本字段的样式。
- **textEditorStyle(_:)**：设置该视图中文本字段的样式：为该视图中的文本编辑器设置样式。
- **TextEditorStyle**：文本编辑器的外观和交互规范。
- **TextEditorStyleConfiguration**：文本编辑器的属性。

## 符合类型

- 默认文本字段样式
- 普通文本字段样式
- 圆形边框文本字段样式
- 方形边框文本字段样式


---
source: https://developer.apple.com/documentation/SwiftUI/TextFieldStyle
crawled: 2025-12-02T17:33:17Z
---

# TextFieldStyle

**Protocol**

A specification for the appearance and interaction of a text field.

## Declaration

```swift
protocol TextFieldStyle
```

## Getting built-in text field styles

- **automatic**: The default text field style, based on the text field’s context.
- **plain**: A text field style with no decoration.
- **roundedBorder**: A text field style with a system-defined rounded border.
- **squareBorder**: A text field style with a system-defined square border.

## Supporting types

- **DefaultTextFieldStyle**: The default text field style, based on the text field’s context.
- **PlainTextFieldStyle**: A text field style with no decoration.
- **RoundedBorderTextFieldStyle**: A text field style with a system-defined rounded border.
- **SquareBorderTextFieldStyle**: A text field style with a system-defined square border.

## Styling views that display text

- **labelStyle(_:)**: Sets the style for labels within this view.
- **LabelStyle**: A type that applies a custom appearance to all labels within a view.
- **LabelStyleConfiguration**: The properties of a label.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **textEditorStyle(_:)**: Sets the style for text editors within this view.
- **TextEditorStyle**: A specification for the appearance and interaction of a text editor.
- **TextEditorStyleConfiguration**: The properties of a text editor.

## Conforming Types

- DefaultTextFieldStyle
- PlainTextFieldStyle
- RoundedBorderTextFieldStyle
- SquareBorderTextFieldStyle

