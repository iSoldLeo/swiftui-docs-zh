--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowInteractionBehavior
抓取时间：2025-12-02T17:21:34Z

---

# WindowInteractionBehavior

**Structure**

启用和禁用窗口交互行为的选项。

## 声明

```swift
struct WindowInteractionBehavior
```

## 概述

将此类型的值与以下视图和场景修改器结合使用，以调整窗口支持的功能：

- [windowDismissBehavior(_:)](View/windowDismissBehavior.zh-Hans.md)

- [windowMinimizeBehavior(_:)](View/windowMinimizeBehavior.zh-Hans.md)

- [windowFullScreenBehavior(_:)](View/windowFullScreenBehavior.zh-Hans.md)

- [windowResizeBehavior(_:)](View/windowResizeBehavior.zh-Hans.md)

- [windowBackgroundDragBehavior(_:)](scene/windowBackgroundDragBehavior.zh-Hans.md)

例如，您可以创建一个自定义的“关于”窗口，该窗口仅允许关闭：

```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("About MyApp", id: "about") {
            AboutView()
                .windowMinimizeBehavior(.disabled)
                .windowResizeBehavior(.disabled)
        }
        .windowResizability(.contentSize)
    }
}
```

## 类型属性

- **automatic**：自动行为。关联的窗口行为将根据其外部组件 `Scene` 的配置而启用或禁用。

- **disabled**：禁用行为。关联的窗口交互行为将被禁用。

- **enabled**：已启用的行为。关联的窗口交互行为将被启用。

## 管理窗口行为

- **WindowManagerRole**：用于定义场景窗口在受管窗口上下文（例如全屏模式和舞台管理器）中使用时的行为选项。

- **windowManagerRole(_:)**：配置从 `self` 派生的窗口在参与受管窗口上下文（例如全屏或舞台管理器）时的角色。

- **windowDismissBehavior(_:)**：配置包含 `self` 的窗口的关闭功能。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowMinimizeBehavior(_:)**：配置包含 `self` 的窗口的最小化功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。

- **windowBackgroundDragBehavior(_:)**：配置拖动窗口背景的行为。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/WindowInteractionBehavior
crawled: 2025-12-02T17:21:34Z
---

# WindowInteractionBehavior

**Structure**

Options for enabling and disabling window interaction behaviors.

## Declaration

```swift
struct WindowInteractionBehavior
```

## Overview

Use values of this type in conjunction with the following view and scene modifiers to adjust the supported functionality for the window:

- [windowDismissBehavior(_:)](View/windowDismissBehavior.zh-Hans.md)
- [windowMinimizeBehavior(_:)](View/windowMinimizeBehavior.zh-Hans.md)
- [windowFullScreenBehavior(_:)](View/windowFullScreenBehavior.zh-Hans.md)
- [windowResizeBehavior(_:)](View/windowResizeBehavior.zh-Hans.md)
- [windowBackgroundDragBehavior(_:)](scene/windowBackgroundDragBehavior.zh-Hans.md)

For example, you can create a custom “About” window which only allows for dismissal:

```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("About MyApp", id: "about") {
            AboutView()
                .windowMinimizeBehavior(.disabled)
                .windowResizeBehavior(.disabled)
        }
        .windowResizability(.contentSize)
    }
}
```

## Type Properties

- **automatic**: The automatic behavior. The associated window behavior will be enabled or disabled depending on the configuration of the enclosing `Scene`.
- **disabled**: The disabled behavior. The associated window interaction behavior will be disabled.
- **enabled**: The enabled behavior. The associated window interaction behavior will be enabled.

## Managing window behavior

- **WindowManagerRole**: Options for defining how a scene’s windows behave when used within a managed window context, such as full screen mode and Stage Manager.
- **windowManagerRole(_:)**: Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.
- **windowDismissBehavior(_:)**: Configures the dismiss functionality for the window enclosing `self`.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowMinimizeBehavior(_:)**: Configures the minimize functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.
- **windowBackgroundDragBehavior(_:)**: Configures the behavior of dragging a window by its background.

## Conforms To

- Sendable
- SendableMetatype

