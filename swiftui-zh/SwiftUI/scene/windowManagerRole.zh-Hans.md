--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowManagerRole(_:)

抓取时间：2025-12-02T17:21:33Z

---

# windowManagerRole(_:)

**实例方法**

配置从 `self` 派生的窗口在参与托管窗口上下文（例如全屏或舞台管理器）时的角色。

## 声明

```swift
nonisolated func windowManagerRole(_ role: WindowManagerRole) -> some Scene

```

## 说明

默认情况下，`Scene` 的类型及其在应用程序定义中的位置将决定其窗口在窗口管理上下文中的行为。

您可以使用此修饰符来覆盖默认行为。

例如，您可以指定辅助场景 `Window` 在全屏和舞台管理器模式下使用主场景的行为：

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

## 管理窗口行为

- **WindowManagerRole**：用于定义场景窗口在受管窗口上下文（例如全屏模式和舞台管理器）中使用时的行为选项。

- **WindowInteractionBehavior**：用于启用和禁用窗口交互行为的选项。

- **windowDismissBehavior(_:)**：配置包含 `self` 的窗口的关闭功能。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowMinimizeBehavior(_:)**：配置包含 `self` 的窗口的最小化功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。

- **windowBackgroundDragBehavior(_:)**：配置拖动窗口背景的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowManagerRole(_:)
crawled: 2025-12-02T17:21:33Z
---

# windowManagerRole(_:)

**Instance Method**

Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.

## Declaration

```swift
nonisolated func windowManagerRole(_ role: WindowManagerRole) -> some Scene

```

## Discussion

By default, the type of `Scene` and its placement within the app’s definition will determine the behavior of its windows within a window management context.

You can use this modifier to override the default behaivor.

For example, you can specify that a secondary `Window` scene should use the principal behavior for full screen and Stage Manager:

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

## Managing window behavior

- **WindowManagerRole**: Options for defining how a scene’s windows behave when used within a managed window context, such as full screen mode and Stage Manager.
- **WindowInteractionBehavior**: Options for enabling and disabling window interaction behaviors.
- **windowDismissBehavior(_:)**: Configures the dismiss functionality for the window enclosing `self`.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowMinimizeBehavior(_:)**: Configures the minimize functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.
- **windowBackgroundDragBehavior(_:)**: Configures the behavior of dragging a window by its background.

