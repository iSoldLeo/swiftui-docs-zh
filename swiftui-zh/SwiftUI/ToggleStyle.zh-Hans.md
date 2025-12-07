--- 来源：https://developer.apple.com/documentation/SwiftUI/ToggleStyle
抓取时间：2025-12-02T17:33:10Z

---

# ToggleStyle

**Protocol**

切换按钮的外观和行为。

## 声明

```swift
@MainActor @preconcurrency protocol ToggleStyle
```

## 概述

要为单个[Toggle](Toggle.zh-Hans.md)或视图层级结构中的所有切换按钮实例配置样式，请使用[toggleStyle(_:)](View/toggleStyle.zh-Hans.md)修饰符。您可以指定内置的切换按钮样式之一，例如[switch](ToggleStyle/switch.zh-Hans.md)或[button](ToggleStyle/button.zh-Hans.md)：

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```

或者，您可以创建并应用自定义样式。

### 自定义样式

要创建自定义样式，请声明一个符合 `ToggleStyle` 协议的类型，并实现所需的 [makeBody(configuration:)](ToggleStyle/makeBody_configuration.zh-Hans.md) 方法。例如，您可以定义一个复选框切换样式：

```swift
struct ChecklistToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        // Return a view that has checklist appearance and behavior.
    }
}
```

在方法内部，使用 `configuration` 参数（它是 [ToggleStyleConfiguration](ToggleStyleConfiguration.zh-Hans.md) 结构的实例）来获取标签和与切换状态的绑定。要查看如何使用这些项来构建具有切换外观和行为的视图的示例，请参阅 [makeBody(configuration:)](ToggleStyle/makeBody_configuration.zh-Hans.md)。

为了方便地使用新样式，请在 `ToggleStyle` 的扩展中声明一个对应的静态变量：

```swift
extension ToggleStyle where Self == ChecklistToggleStyle {
    static var checklist: ChecklistToggleStyle { .init() }
}
```

然后，您可以使用自定义样式：

```swift
Toggle(activity.name, isOn: $activity.isComplete)
    .toggleStyle(.checklist)
```

如果类型的基本声明中包含了符合性声明，则符合此协议的类型将继承来自协议的隔离性：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下，隔离到主 Actor，但这不是必需的。在扩展中声明符合性声明即可选择退出主 Actor 隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置切换样式

- **automatic**：默认切换样式。

- **button**：一种切换样式，显示为按钮，其标签作为标题。

- **checkbox**：一种切换样式，显示一个复选框，其后跟标签。

- **switch**：一种切换样式，显示一个前置标签和一个后置开关。

## 创建自定义切换样式

- **makeBody(configuration:)**：创建一个视图，用于表示切换开关的主体。

- **ToggleStyleConfiguration**：切换开关实例的属性。

- **ToggleStyle.Configuration**：切换开关实例的属性。

- **Body**：一个视图，用于表示切换开关的外观和交互。

## 支持的类型

- **DefaultToggleStyle**：默认切换样式。

- **ButtonToggleStyle**：显示为按钮的切换样式，其标签作为标题。

- **CheckboxToggleStyle**：显示复选框及其标签的切换样式。

- **SwitchToggleStyle**：显示前置标签和尾部开关的切换样式。

## 设置切换样式

- **toggleStyle(_:)**：设置视图层次结构中切换的样式。

- **ToggleStyleConfiguration**：切换实例的属性。

## 符合规范的类型

- ButtonToggleStyle

- CheckboxToggleStyle

- DefaultToggleStyle

- SwitchToggleStyle


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle
crawled: 2025-12-02T17:33:10Z
---

# ToggleStyle

**Protocol**

The appearance and behavior of a toggle.

## Declaration

```swift
@MainActor @preconcurrency protocol ToggleStyle
```

## Overview

To configure the style for a single [Toggle](Toggle.zh-Hans.md) or for all toggle instances in a view hierarchy, use the [toggleStyle(_:)](View/toggleStyle.zh-Hans.md) modifier. You can specify one of the built-in toggle styles, like [switch](ToggleStyle/switch.zh-Hans.md) or [button](ToggleStyle/button.zh-Hans.md):

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```

Alternatively, you can create and apply a custom style.

### Custom styles

To create a custom style, declare a type that conforms to the `ToggleStyle` protocol and implement the required [makeBody(configuration:)](ToggleStyle/makeBody_configuration.zh-Hans.md) method. For example, you can define a checklist toggle style:

```swift
struct ChecklistToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        // Return a view that has checklist appearance and behavior.
    }
}
```

Inside the method, use the `configuration` parameter, which is an instance of the [ToggleStyleConfiguration](ToggleStyleConfiguration.zh-Hans.md) structure, to get the label and a binding to the toggle state. To see examples of how to use these items to construct a view that has the appearance and behavior of a toggle, see [makeBody(configuration:)](ToggleStyle/makeBody_configuration.zh-Hans.md).

To provide easy access to the new style, declare a corresponding static variable in an extension to `ToggleStyle`:

```swift
extension ToggleStyle where Self == ChecklistToggleStyle {
    static var checklist: ChecklistToggleStyle { .init() }
}
```

You can then use your custom style:

```swift
Toggle(activity.name, isOn: $activity.isComplete)
    .toggleStyle(.checklist)
```

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

## Getting built-in toggle styles

- **automatic**: The default toggle style.
- **button**: A toggle style that displays as a button with its label as the title.
- **checkbox**: A toggle style that displays a checkbox followed by its label.
- **switch**: A toggle style that displays a leading label and a trailing switch.

## Creating custom toggle styles

- **makeBody(configuration:)**: Creates a view that represents the body of a toggle.
- **ToggleStyleConfiguration**: The properties of a toggle instance.
- **ToggleStyle.Configuration**: The properties of a toggle instance.
- **Body**: A view that represents the appearance and interaction of a toggle.

## Supporting types

- **DefaultToggleStyle**: The default toggle style.
- **ButtonToggleStyle**: A toggle style that displays as a button with its label as the title.
- **CheckboxToggleStyle**: A toggle style that displays a checkbox followed by its label.
- **SwitchToggleStyle**: A toggle style that displays a leading label and a trailing switch.

## Styling toggles

- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.
- **ToggleStyleConfiguration**: The properties of a toggle instance.

## Conforming Types

- ButtonToggleStyle
- CheckboxToggleStyle
- DefaultToggleStyle
- SwitchToggleStyle

