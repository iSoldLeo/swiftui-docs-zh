---
来源： https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate
抓取时间： 2025-12-02T17:32:03Z
---

# ControlWidgetTemplate

**Protocol**

描述控件部件内容的类型。

### 声明

```swift
@MainActor @preconcurrency protocol ControlWidgetTemplate
```

## 概览

使用模板定义控件是为了确保控件在所有尺寸和所有系统空间中都能正常显示。这些模板使用简单的 SwiftUI 视图（如 [Label](Label.zh-Hans.md)、[Text](Text.zh-Hans.md) 和 [Image](Image.zh-Hans.md)）定义图像（特别是符号图像）和文本；并使用[tint(_:)](ControlWidgetTemplate/tint.zh-Hans.md) 修改器定义颜色。

如果符合本协议的类型的基本声明中包含了本协议，则该类型将继承`@preconcurrency @MainActor` 隔离：

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

## 关联类型

- **Body**：代表此模板主体的控制 widget 模板类型。

## 实例属性

- **body**：该控件部件的内容和行为。

### 实例方法

- **disabled(_:)**：决定人们是否可以与此控件进行交互。
- **privacySensitive(_:)**：将控件模板标记为包含敏感的私人用户数据。
- **tint(_:)**：设置此控制模板内的色调颜色。

## 组成控件部件

- **ControlWidget**：控制中心、锁屏和操作按钮等系统空间中显示的控制 widget 的配置和内容。
- **ControlWidgetConfiguration**：描述控制 widget 内容的类型。
- **EmptyControlWidgetConfiguration**：一个空的控件部件配置。
- **ControlWidgetConfigurationBuilder**：用于构建控件 widget 主体的自定义属性。
- **EmptyControlWidgetTemplate**：一个空的控件部件模板。
- **ControlWidgetTemplateBuilder**：用于构建控件 widget 模板主体的自定义属性。
- **controlWidgetActionHint(_:)**：修改后的标签所描述的控件的操作提示。
- **controlWidgetStatus(_:)**：被修改标签描述的控件的状态。

## 符合类型

- 空控件部件模板（EmptyControlWidgetTemplate


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplate
crawled: 2025-12-02T17:32:03Z
---

# ControlWidgetTemplate

**Protocol**

A type that describes a control widget’s content.

## Declaration

```swift
@MainActor @preconcurrency protocol ControlWidgetTemplate
```

## Overview

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

- **Body**: The type of control widget template representing the body of this template.

## Instance Properties

- **body**: The content and behavior of this control widget.

## Instance Methods

- **disabled(_:)**: Determines whether people can interact with this control.
- **privacySensitive(_:)**: Marks the control template as containing sensitive, private user data.
- **tint(_:)**: Sets the tint color within this control template.

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

## Conforming Types

- EmptyControlWidgetTemplate

