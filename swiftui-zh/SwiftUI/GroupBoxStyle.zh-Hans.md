--- 来源：https://developer.apple.com/documentation/SwiftUI/GroupBoxStyle
抓取时间：2025-12-02T17:33:33Z
---

# GroupBoxStyle

**Protocol**

一种类型，用于指定视图层级结构中所有分组框的外观和交互方式。

## 声明

```swift
@MainActor @preconcurrency protocol GroupBoxStyle
```

## 概述

要为视图层级结构配置当前的 `GroupBoxStyle`，请使用 [groupBoxStyle(_:)](View/groupBoxStyle.zh-Hans.md) 修饰符。

如果类型的基本声明中包含符合性声明，则符合此协议的类型将继承协议的 `@preconcurrency @MainActor` 隔离性：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下隔离到主参与者，但这不是必需的。在扩展中声明一致性以选择退出主参与者隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置分组框样式

- **automatic**：分组框视图的默认样式。

## 创建自定义分组框样式

- **makeBody(configuration:)**：创建一个表示分组框主体的视图。

- **GroupBoxStyle.Configuration**：分组框实例的属性。

- **Body**：表示分组框主体的视图。

## 支持的类型

- **DefaultGroupBoxStyle**：分组框视图的默认样式。

## 设置分组样式

- **controlGroupStyle(_:)**：设置此视图中控件组的样式。

- **ControlGroupStyle**：定义视图层次结构中所有控件组的实现。

- **ControlGroupStyleConfiguration**：控件组的属性。

- **formStyle(_:)**：设置视图层次结构中窗体的样式。

- **FormStyle**：窗体的外观和行为。

- **FormStyleConfiguration**：窗体实例的属性。

- **groupBoxStyle(_:)**：设置此视图中分组框的样式。

- **GroupBoxStyleConfiguration**：分组框实例的属性。

- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。

- **IndexViewStyle**：定义视图层次结构中所有 `IndexView` 实例的实现。

- **labeledContentStyle(_:)**：设置带标签内容的样式。

- **LabeledContentStyle**：带标签内容实例的外观和行为。

- **LabeledContentStyleConfiguration**：带标签内容实例的属性。

## 符合规范的类型

- DefaultGroupBoxStyle


---
source: https://developer.apple.com/documentation/SwiftUI/GroupBoxStyle
crawled: 2025-12-02T17:33:33Z
---

# GroupBoxStyle

**Protocol**

A type that specifies the appearance and interaction of all group boxes within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol GroupBoxStyle
```

## Overview

To configure the current `GroupBoxStyle` for a view hierarchy, use the [groupBoxStyle(_:)](View/groupBoxStyle.zh-Hans.md) modifier.

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

## Getting built-in group box styles

- **automatic**: The default style for group box views.

## Creating custom group box styles

- **makeBody(configuration:)**: Creates a view representing the body of a group box.
- **GroupBoxStyle.Configuration**: The properties of a group box instance.
- **Body**: A view that represents the body of a group box.

## Supporting types

- **DefaultGroupBoxStyle**: The default style for group box views.

## Styling groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
- **ControlGroupStyle**: Defines the implementation of all control groups within a view hierarchy.
- **ControlGroupStyleConfiguration**: The properties of a control group.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **FormStyle**: The appearance and behavior of a form.
- **FormStyleConfiguration**: The properties of a form instance.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.
- **GroupBoxStyleConfiguration**: The properties of a group box instance.
- **indexViewStyle(_:)**: Sets the style for the index view within the current environment.
- **IndexViewStyle**: Defines the implementation of all `IndexView` instances within a view hierarchy.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **LabeledContentStyle**: The appearance and behavior of a labeled content instance..
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

## Conforming Types

- DefaultGroupBoxStyle

