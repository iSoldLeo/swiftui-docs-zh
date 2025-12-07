---
来源： https://developer.apple.com/documentation/SwiftUI/FormStyle
抓取时间： 2025-12-02T17:33:31Z
---

# FormStyle

**Protocol**

表单的外观和行为。

## 声明

```swift
@MainActor @preconcurrency protocol FormStyle
```

## 概览

要为单一[Form](Form.zh-Hans.md) 或视图层次结构中的所有表单实例配置样式，请使用[formStyle(_:)](View/formStyle.zh-Hans.md) 修改器。

如果符合本协议的类型的基本声明中包含了本协议，则该类型将继承`@preconcurrency @MainActor` 隔离协议：

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

## 获取内置表单样式

- **automatic**：默认表单样式。
- **columns**：默认表单样式：一种非滚动表单样式，标签列尾部对齐，数值列前部对齐。
- **grouped**：分组行的表格样式。

## 创建自定义表单样式

- **makeBody(configuration:)**：创建表示表单正文的视图。
- **FormStyle.Configuration**：表单实例的属性。
- **Body**：表单实例的属性：表示表单的外观和交互的视图。

## 支持类型

- **AutomaticFormStyle**：默认表单样式。
- **ColumnsFormStyle**：默认表单样式：一种非滚动表单样式，标签列尾部对齐，数值列前部对齐。
- **GroupedFormStyle**：具有分组行的表格样式。

## 分组样式

- **controlGroupStyle(_:)**：设置该视图中控件组的样式。
- **ControlGroupStyle**：定义视图层次结构中所有控制组的实现。
- **ControlGroupStyleConfiguration**：控制组的属性。
- **formStyle(_:)**：为视图层次结构中的窗体设置样式。
- **FormStyleConfiguration**：表单实例的属性。
- **groupBoxStyle(_:)**：设置此视图中组框的样式。
- **GroupBoxStyle**：指定视图层次结构中所有组框的外观和交互的类型。
- **GroupBoxStyleConfiguration**：组框实例的属性。
- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。
- **IndexViewStyle**：定义视图层次结构中所有`IndexView` 实例的实现。
- **labeledContentStyle(_:)**：为标签内容设置样式。
- **LabeledContentStyle**：标注内容实例的外观和行为。
- **LabeledContentStyleConfiguration**：标注内容实例的属性。

## 符合类型

- 自动表格样式
- 列式表格样式
- 分组表格样式


---
source: https://developer.apple.com/documentation/SwiftUI/FormStyle
crawled: 2025-12-02T17:33:31Z
---

# FormStyle

**Protocol**

The appearance and behavior of a form.

## Declaration

```swift
@MainActor @preconcurrency protocol FormStyle
```

## Overview

To configure the style for a single [Form](Form.zh-Hans.md) or for all form instances in a view hierarchy, use the [formStyle(_:)](View/formStyle.zh-Hans.md) modifier.

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

## Getting built-in form styles

- **automatic**: The default form style.
- **columns**: A non-scrolling form style with a trailing aligned column of labels next to a leading aligned column of values.
- **grouped**: A form style with grouped rows.

## Creating custom form styles

- **makeBody(configuration:)**: Creates a view that represents the body of a form.
- **FormStyle.Configuration**: The properties of a form instance.
- **Body**: A view that represents the appearance and interaction of a form.

## Supporting types

- **AutomaticFormStyle**: The default form style.
- **ColumnsFormStyle**: A non-scrolling form style with a trailing aligned column of labels next to a leading aligned column of values.
- **GroupedFormStyle**: A form style with grouped rows.

## Styling groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
- **ControlGroupStyle**: Defines the implementation of all control groups within a view hierarchy.
- **ControlGroupStyleConfiguration**: The properties of a control group.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **FormStyleConfiguration**: The properties of a form instance.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.
- **GroupBoxStyle**: A type that specifies the appearance and interaction of all group boxes within a view hierarchy.
- **GroupBoxStyleConfiguration**: The properties of a group box instance.
- **indexViewStyle(_:)**: Sets the style for the index view within the current environment.
- **IndexViewStyle**: Defines the implementation of all `IndexView` instances within a view hierarchy.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **LabeledContentStyle**: The appearance and behavior of a labeled content instance..
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

## Conforming Types

- AutomaticFormStyle
- ColumnsFormStyle
- GroupedFormStyle

