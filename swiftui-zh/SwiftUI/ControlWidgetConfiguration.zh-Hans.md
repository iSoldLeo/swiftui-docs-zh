---
来源： https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfiguration
抓取时间： 2025-12-02T17:32:01Z
---

# ControlWidgetConfiguration

**Protocol**

描述控件部件内容的类型。

### 声明

```swift
@MainActor @preconcurrency protocol ControlWidgetConfiguration
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

## 关联类型

- **Body**：代表此配置主体的控制 widget 配置类型。

## 实例属性

- **body**：控件的内容和行为。

### 实例方法

- **description(_:)**：使用指定的字符串设置用户添加或编辑控件时显示的描述。
- **displayName(_:)**：使用指定的字符串设置用户添加或编辑控件时显示的控件名称。
- **promptsForUserConfiguration()**：指定控件的配置 UI 应在 widget 添加后自动显示。
- **pushHandler(_:)**：注册一种可处理推送令牌更改的类型，用于此类型的控件。

## 组成控件部件

- **ControlWidget**：控制中心、锁屏和操作按钮等系统空间中显示的控制 widget 的配置和内容。
- **EmptyControlWidgetConfiguration**：一个空的控制 widget 配置。
- **ControlWidgetConfigurationBuilder**：用于构建控制 widget 主体的自定义属性。
- **ControlWidgetTemplate**：描述控件 widget 内容的类型。
- **EmptyControlWidgetTemplate**：一个空的控件部件模板。
- **ControlWidgetTemplateBuilder**：用于构建控件 widget 模板主体的自定义属性。
- **controlWidgetActionHint(_:)**：修改后的标签所描述的控件的操作提示。
- **controlWidgetStatus(_:)**：被修改标签描述的控件的状态。

## 符合类型

- 空控件部件配置（EmptyControlWidgetConfiguration


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfiguration
crawled: 2025-12-02T17:32:01Z
---

# ControlWidgetConfiguration

**Protocol**

A type that describes a control widget’s content.

## Declaration

```swift
@MainActor @preconcurrency protocol ControlWidgetConfiguration
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

## Associated Types

- **Body**: The type of control widget configuration representing the body of this configuration.

## Instance Properties

- **body**: The content and behavior of the control.

## Instance Methods

- **description(_:)**: Sets the description shown for the control when a user adds or edits it, using the specified string.
- **displayName(_:)**: Sets the name shown for the control when a user adds or edits it, using the specified string.
- **promptsForUserConfiguration()**: Specifies that a control’s configuration UI should be automatically presented after the widget is added.
- **pushHandler(_:)**: Register a type that can handle push tokens changing for controls of this type.

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

## Conforming Types

- EmptyControlWidgetConfiguration

