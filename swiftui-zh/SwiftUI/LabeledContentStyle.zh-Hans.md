---
来源： https://developer.apple.com/documentation/SwiftUI/LabeledContentStyle
抓取时间： 2025-12-02T17:33:37Z
---

# LabeledContentStyle

**Protocol**

标签内容实例的外观和行为。

## 声明

```swift
@MainActor @preconcurrency protocol LabeledContentStyle
```

## 概览

使用 [labeledContentStyle(_:)](View/labeledContentStyle.zh-Hans.md) 为视图设置样式。

如果符合`@preconcurrency @MainActor` 协议的类型的基本声明中包含了该协议，则该类型将继承`@preconcurrency @MainActor` 隔离协议：

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

## 获取内置标签内容样式

- **automatic**：根据当前上下文自动调整外观的标签内容样式。

## 创建自定义标签内容样式

- **makeBody(configuration:)**：创建表示标注内容正文的视图。
- **LabeledContentStyle.Configuration**：标注内容实例的属性。
- **Body**：表示标签内容的外观和行为的视图。

## 支持类型

- **AutomaticLabeledContentStyle**：默认的标注内容样式。

## 样式组

- **controlGroupStyle(_:)**：设置该视图中控件组的样式。
- **ControlGroupStyle**：定义视图层次结构中所有控制组的实现。
- **ControlGroupStyleConfiguration**：控制组的属性。
- **formStyle(_:)**：为视图层次结构中的窗体设置样式。
- **FormStyle**：表单的外观和行为。
- **FormStyleConfiguration**：表单实例的属性。
- **groupBoxStyle(_:)**：表单实例的属性：为该视图中的组框设置样式。
- **GroupBoxStyle**：指定视图层次结构中所有组框的外观和交互的类型。
- **GroupBoxStyleConfiguration**：组框实例的属性。
- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。
- **IndexViewStyle**：定义视图层次结构中所有`IndexView` 实例的实现。
- **labeledContentStyle(_:)**：为标签内容设置样式。
- **LabeledContentStyleConfiguration**：标注内容实例的属性。

## 符合类型

- 自动标注内容样式（AutomaticLabeledContentStyle


---
source: https://developer.apple.com/documentation/SwiftUI/LabeledContentStyle
crawled: 2025-12-02T17:33:37Z
---

# LabeledContentStyle

**Protocol**

The appearance and behavior of a labeled content instance..

## Declaration

```swift
@MainActor @preconcurrency protocol LabeledContentStyle
```

## Overview

Use [labeledContentStyle(_:)](View/labeledContentStyle.zh-Hans.md) to set a style on a view.

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

## Getting built-in labeled content styles

- **automatic**: A labeled content style that resolves its appearance automatically based on the current context.

## Creating custom labeled content styles

- **makeBody(configuration:)**: Creates a view that represents the body of labeled content.
- **LabeledContentStyle.Configuration**: The properties of a labeled content instance.
- **Body**: A view that represents the appearance and behavior of labeled content.

## Supporting types

- **AutomaticLabeledContentStyle**: The default labeled content style.

## Styling groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
- **ControlGroupStyle**: Defines the implementation of all control groups within a view hierarchy.
- **ControlGroupStyleConfiguration**: The properties of a control group.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **FormStyle**: The appearance and behavior of a form.
- **FormStyleConfiguration**: The properties of a form instance.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.
- **GroupBoxStyle**: A type that specifies the appearance and interaction of all group boxes within a view hierarchy.
- **GroupBoxStyleConfiguration**: The properties of a group box instance.
- **indexViewStyle(_:)**: Sets the style for the index view within the current environment.
- **IndexViewStyle**: Defines the implementation of all `IndexView` instances within a view hierarchy.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

## Conforming Types

- AutomaticLabeledContentStyle

