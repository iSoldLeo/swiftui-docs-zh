--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowManagerRole
抓取时间：2025-12-02T17:21:32Z

---

# WindowManagerRole

**Structure**

用于定义场景窗口在托管窗口上下文（例如全屏模式和舞台管理器）中的行为选项。

## 声明

```swift
struct WindowManagerRole
```

## 概述

将此类型的值与 [windowManagerRole(_:)](scene/windowManagerRole.zh-Hans.md) 修饰符结合使用，以覆盖默认的系统行为。

例如，您可以指定辅助场景 `Window` 应使用主场景角色来实现全屏和舞台管理器：

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        Window("Organizer", id: "organizer") {
            OrganizerView()
        }
        .windowManagerRole(.principal)
    }
}
```

## 类型属性

- **associated**：关联角色。源自此场景的窗口可以与具有 `.principal` 角色的窗口一起显示在全屏或舞台管理器模式下，但它们本身并不参与这些模式。

- **automatic**：自动角色。场景的类型和配置将用于确定其窗口在全屏和舞台管理器模式下的行为。

- **principal**：主要角色。源自此场景的窗口将显示在全屏模式下（如果已启用），或者显示在舞台管理器模式下。

## 管理窗口行为

- **windowManagerRole(_:)**：配置源自 `self` 的窗口在参与受管窗口上下文（例如全屏或舞台管理器）时的角色。

- **WindowInteractionBehavior**：用于启用和禁用窗口交互行为的选项。

- **windowDismissBehavior(_:)**：配置包含 `self` 的窗口的关闭功能。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowMinimizeBehavior(_:)**：配置包含 `self` 的窗口的最小化功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。

- **windowBackgroundDragBehavior(_:)**：配置拖动窗口背景的行为。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/WindowManagerRole
crawled: 2025-12-02T17:21:32Z
---

# WindowManagerRole

**Structure**

Options for defining how a scene’s windows behave when used within a managed window context, such as full screen mode and Stage Manager.

## Declaration

```swift
struct WindowManagerRole
```

## Overview

Use values of this type in conjunction with the [windowManagerRole(_:)](scene/windowManagerRole.zh-Hans.md) modifier to override the default system behavior.

For example, you can specify that a secondary `Window` scene should use the principal role for full screen and Stage Manager:

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        Window("Organizer", id: "organizer") {
            OrganizerView()
        }
        .windowManagerRole(.principal)
    }
}
```

## Type Properties

- **associated**: The associated role. Windows derived from this scene can be shown alongside windows with a `.principal` role in either full screen or Stage Manager, but do not participate in those modes on their own.
- **automatic**: The automatic role. The type and configuration of the scene will be used to determine how its windows behave in full screen and Stage Manager.
- **principal**: The principal role. Windows derived from this scene will show in full screen, if enabled, or in Stage Manager.

## Managing window behavior

- **windowManagerRole(_:)**: Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.
- **WindowInteractionBehavior**: Options for enabling and disabling window interaction behaviors.
- **windowDismissBehavior(_:)**: Configures the dismiss functionality for the window enclosing `self`.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowMinimizeBehavior(_:)**: Configures the minimize functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.
- **windowBackgroundDragBehavior(_:)**: Configures the behavior of dragging a window by its background.

## Conforms To

- Sendable
- SendableMetatype

