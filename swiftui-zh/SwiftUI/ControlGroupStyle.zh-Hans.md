--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle
抓取时间：2025-12-02T17:33:29Z

---

# ControlGroupStyle

**Protocol**

定义视图层次结构中所有控制组的实现。

## 声明

```swift
@MainActor @preconcurrency protocol ControlGroupStyle
```

## 概述

要为视图层次结构配置当前的 `ControlGroupStyle`，请使用 [controlGroupStyle(_:)](View/controlGroupStyle.zh-Hans.md) 修饰符。

如果类型的基本声明中包含此协议，则符合此协议的类型将继承协议的 `@preconcurrency @MainActor` 隔离性：

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

## 获取内置控件组样式

- **automatic**：默认控件组样式。

- **compactMenu**：一种控件组样式，当用户按下控件时，其内容以紧凑菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **menu**：一种控件组样式，当用户按下控件时，其内容以菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **navigation**：导航控件组样式。

- **palette**：一种控件组样式，其内容以调色板的形式呈现。

## 创建自定义控件组样式

- **makeBody(configuration:)**：创建一个表示控件组主体的视图。

- **ControlGroupStyle.Configuration**：正在创建的 `ControlGroup` 实例的属性。

- **Body**：一个表示控件组主体的视图。

## 支持的类型

- **AutomaticControlGroupStyle**：默认控件组样式。

- **CompactMenuControlGroupStyle**：一种控件组样式，当用户按下控件时，其内容显示为简洁菜单；当嵌套在更大的菜单中时，则显示为子菜单。

- **MenuControlGroupStyle**：一种控件组样式，当用户按下控件时，其内容显示为菜单；当嵌套在更大的菜单中时，则显示为子菜单。

- **NavigationControlGroupStyle**：导航控件组样式。

- **PaletteControlGroupStyle**：将内容显示为调色板的控件组样式。

## 设置组样式

- **controlGroupStyle(_:)**：设置此视图中控件组的样式。

- **ControlGroupStyleConfiguration**：控件组的属性。

- **formStyle(_:)**：设置视图层次结构中表单的样式。

- **FormStyle**：表单的外观和行为。

- **FormStyleConfiguration**：表单实例的属性。

- **groupBoxStyle(_:)**：设置此视图中分组框的样式。

- **GroupBoxStyle**：指定视图层次结构中所有分组框的外观和交互方式的类型。

- **GroupBoxStyleConfiguration**：分组框实例的属性。

- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。

- **IndexViewStyle**：定义视图层次结构中所有 `IndexView` 实例的实现。

- **labeledContentStyle(_:)**：设置带标签内容的样式。

- **LabeledContentStyle**：带标签内容实例的外观和行为。

- **LabeledContentStyleConfiguration**：带标签内容实例的属性。

## 符合规范的类型

- AutomaticControlGroupStyle

- CompactMenuControlGroupStyle

- MenuControlGroupStyle

- NavigationControlGroupStyle

- PaletteControlGroupStyle


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle
crawled: 2025-12-02T17:33:29Z
---

# ControlGroupStyle

**Protocol**

Defines the implementation of all control groups within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol ControlGroupStyle
```

## Overview

To configure the current `ControlGroupStyle` for a view hierarchy, use the [controlGroupStyle(_:)](View/controlGroupStyle.zh-Hans.md) modifier.

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

## Getting built-in control group styles

- **automatic**: The default control group style.
- **compactMenu**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **menu**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **navigation**: The navigation control group style.
- **palette**: A control group style that presents its content as a palette.

## Creating custom control group styles

- **makeBody(configuration:)**: Creates a view representing the body of a control group.
- **ControlGroupStyle.Configuration**: The properties of a `ControlGroup` instance being created.
- **Body**: A view representing the body of a control group.

## Supporting types

- **AutomaticControlGroupStyle**: The default control group style.
- **CompactMenuControlGroupStyle**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **MenuControlGroupStyle**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **NavigationControlGroupStyle**: The navigation control group style.
- **PaletteControlGroupStyle**: A control group style that presents its content as a palette.

## Styling groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
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
- **LabeledContentStyle**: The appearance and behavior of a labeled content instance..
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

## Conforming Types

- AutomaticControlGroupStyle
- CompactMenuControlGroupStyle
- MenuControlGroupStyle
- NavigationControlGroupStyle
- PaletteControlGroupStyle

