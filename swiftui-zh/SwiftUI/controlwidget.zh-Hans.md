--- 来源：https://developer.apple.com/documentation/swiftui/controlwidget

抓取时间：2025-12-04T13:10:20Z

---

# ControlWidget

**Protocol**

用于在系统空间（例如控制中心、锁定屏幕和操作按钮）中显示的控件组件的配置和内容。

## 声明

```swift
@MainActor @preconcurrency protocol ControlWidget
```

## 概述

控件允许用户快速查看您的应用或其附件的状态，并执行快速操作，而无需打开您的应用。用户可以添加、配置和排列控件以满足其个性化需求。您可以提供多种类型的控件，每种控件代表一种特定的操作。

控件包含三个关键组件：

- 配置：用于确定控件是否可配置、标识控件以及定义提供控件内容的 SwiftUI 模板。

- 一个值提供程序，用于定义控件在预览和实际渲染时的值。

- WidgetKit 用于显示控件的模板。

控件使用模板定义，以确保它们在所有尺寸和所有可能显示它们的系统空间中都能正常工作。这些模板使用简单的 SwiftUI 视图（例如 [Label](Label.zh-Hans.md)、[Text](Text.zh-Hans.md) 和 [Image](Image.zh-Hans.md)）定义图像（特别是符号图像）和文本；并使用 [tint(_:)](ControlWidgetTemplate/tint.zh-Hans.md) 修饰符来着色。

如果符合此协议的类型在其基本声明中包含该协议，则该类型将从协议继承 `@preconcurrency @MainActor` 隔离：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下，隔离到主要参与者，但这不是必需的。在扩展中声明一致性，以选择退出主 Actor 隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 关联类型

- **Body**：表示此控件内容的配置类型。

## 初始化器

- **init()**：使用 `body` 作为其内容创建控件。

## 实例属性

- **body**：控件的内容和行为。

## 类型方法

- **main()**

## 组合控件组件

- **ControlWidgetConfiguration**：描述控件组件内容的类型。

- **EmptyControlWidgetConfiguration**：空的控件组件配置。

- **ControlWidgetConfigurationBuilder**：用于构建控件主体的自定义属性。

- **ControlWidgetTemplate**：用于描述控件内容的类型。

- **EmptyControlWidgetTemplate**：空的控件模板。

- **ControlWidgetTemplateBuilder**：用于构建控件模板主体的自定义属性。

- **controlWidgetActionHint(_:)**：由修改标签描述的控件的操作提示。

- **controlWidgetStatus(_:)**：由修改标签描述的控件的状态。


---
source: https://developer.apple.com/documentation/swiftui/controlwidget
crawled: 2025-12-04T13:10:20Z
---

# ControlWidget

**Protocol**

The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.

## Declaration

```swift
@MainActor @preconcurrency protocol ControlWidget
```

## Overview

Controls allow users to quickly read the state of your app or its accessories, and take quick actions, without having to open your app. Users can add, configure, and arrange controls to suit their individual needs. You can provide multiple types of controls, each representing a specific kind of action.

There are three key components to a control:

- A configuration that determines whether the control is configurable, identifies the control, and defines the SwiftUI template that provides the control’s content.
- A value provider that defines the value of the control when being previewed and when being actually rendered
- The template used by WidgetKit to display the control.

Controls are defined using templates in order to ensure that they control will work at all sizes and in all system spaces in which they might be displayed. These templates define images (specifically, symbol images) and text using simple SwiftUI views like [Label](Label.zh-Hans.md), [Text](Text.zh-Hans.md), and [Image](Image.zh-Hans.md); and tint colors using the [tint(_:)](ControlWidgetTemplate/tint.zh-Hans.md) modifier.

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

## Associated Types

- **Body**: The type of configuration representing the content of this control.

## Initializers

- **init()**: Creates a control using `body` as its content.

## Instance Properties

- **body**: The content and behavior of the control.

## Type Methods

- **main()**

## Composing control widgets

- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

