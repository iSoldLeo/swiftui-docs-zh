--- 来源：https://developer.apple.com/documentation/SwiftUI/LabelStyle
抓取时间：2025-12-02T17:33:16Z

---

# LabelStyle

**Protocol**

一种为视图中的所有标签应用自定义外观的类型。

## 声明

```swift
@MainActor @preconcurrency protocol LabelStyle
```

## 概述

要为视图层次结构配置当前标签样式，请使用 [labelStyle(_:)](View/labelStyle.zh-Hans.md) 修饰符。

如果类型的基本声明中包含符合性声明，则符合此协议的类型将继承来自协议的 `@preconcurrency @MainActor` 隔离性：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下隔离到主 Actor，但这不是必需的。在扩展中声明一致性以选择退出主 Actor 隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置标签样式

- **automatic**：一种标签样式，可根据当前上下文自动解析其外观。

- **iconOnly**：一种标签样式，仅显示标签图标。

- **titleAndIcon**：一种标签样式，使用系统标准布局同时显示标签标题和图标。

- **titleOnly**：一种标签样式，仅显示标签标题。

## 创建自定义标签样式

- **makeBody(configuration:)**：创建一个表示标签主体的视图。

- **LabelStyle.Configuration**：标签的属性。

- **Body**：表示标签主体的视图。

## 支持的类型

- **DefaultLabelStyle**：当前上下文中的默认标签样式。

- **IconOnlyLabelStyle**：仅显示标签图标的标签样式。

- **TitleAndIconLabelStyle**：使用系统标准布局同时显示标签标题和图标的标签样式。

- **TitleOnlyLabelStyle**：仅显示标签标题的标签样式。

## 设置显示文本的视图样式

- **labelStyle(_:)**：设置此视图中标签的样式。

- **LabelStyleConfiguration**：标签的属性。

- **textFieldStyle(_:)**：设置此视图中文本字段的样式。

- **TextFieldStyle**：文本字段的外观和交互规范。

- **textEditorStyle(_:)**：设置此视图中文本编辑器的样式。

- **TextEditorStyle**：文本编辑器的外观和交互规范。

- **TextEditorStyleConfiguration**：文本编辑器的属性。

## 符合规范的类型

- DefaultLabelStyle

- IconOnlyLabelStyle

- TitleAndIconLabelStyle

- TitleOnlyLabelStyle


---
source: https://developer.apple.com/documentation/SwiftUI/LabelStyle
crawled: 2025-12-02T17:33:16Z
---

# LabelStyle

**Protocol**

A type that applies a custom appearance to all labels within a view.

## Declaration

```swift
@MainActor @preconcurrency protocol LabelStyle
```

## Overview

To configure the current label style for a view hierarchy, use the [labelStyle(_:)](View/labelStyle.zh-Hans.md) modifier.

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

## Getting built-in label styles

- **automatic**: A label style that resolves its appearance automatically based on the current context.
- **iconOnly**: A label style that only displays the icon of the label.
- **titleAndIcon**: A label style that shows both the title and icon of the label using a system-standard layout.
- **titleOnly**: A label style that only displays the title of the label.

## Creating custom label styles

- **makeBody(configuration:)**: Creates a view that represents the body of a label.
- **LabelStyle.Configuration**: The properties of a label.
- **Body**: A view that represents the body of a label.

## Supporting types

- **DefaultLabelStyle**: The default label style in the current context.
- **IconOnlyLabelStyle**: A label style that only displays the icon of the label.
- **TitleAndIconLabelStyle**: A label style that shows both the title and icon of the label using a system-standard layout.
- **TitleOnlyLabelStyle**: A label style that only displays the title of the label.

## Styling views that display text

- **labelStyle(_:)**: Sets the style for labels within this view.
- **LabelStyleConfiguration**: The properties of a label.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **TextFieldStyle**: A specification for the appearance and interaction of a text field.
- **textEditorStyle(_:)**: Sets the style for text editors within this view.
- **TextEditorStyle**: A specification for the appearance and interaction of a text editor.
- **TextEditorStyleConfiguration**: The properties of a text editor.

## Conforming Types

- DefaultLabelStyle
- IconOnlyLabelStyle
- TitleAndIconLabelStyle
- TitleOnlyLabelStyle

