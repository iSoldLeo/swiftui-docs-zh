--- 来源：https://developer.apple.com/documentation/SwiftUI/View/windowDismissBehavior(_:)

抓取时间：2025-11-30T21:06:38Z

---

# windowDismissBehavior(_:)

**实例方法**

配置包含 `self` 的窗口的关闭功能。

## 声明

```swift
nonisolated func windowDismissBehavior(_ behavior: WindowInteractionBehavior) -> some View

```

## 参数

- **behavior**：关闭行为。

## 说明

默认情况下，窗口的关闭功能由场景及其应用的任何修饰符决定。

您可以使用此修饰符来覆盖默认行为。

例如，您可以创建一个欢迎工作流程窗口，禁用关闭功能：

```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("Welcome", id: "welcome") {
            WelcomeView()
                .windowDismissBehavior(.disabled)
        }
    }
}
```

## 管理窗口行为

- **WindowManagerRole**：用于定义场景窗口在受管窗口上下文（例如全屏模式和舞台管理器）中使用时的行为选项。

- **windowManagerRole(_:)**：配置从 `self` 派生的窗口在参与受管窗口上下文（例如全屏或舞台管理器）时的角色。

- **WindowInteractionBehavior**：用于启用和禁用窗口交互行为的选项。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowMinimizeBehavior(_:)**：配置包含 `self` 的窗口的最小化功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。

- **windowBackgroundDragBehavior(_:)**：配置拖动窗口背景的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/windowDismissBehavior(_:)
crawled: 2025-11-30T21:06:38Z
---

# windowDismissBehavior(_:)

**Instance Method**

Configures the dismiss functionality for the window enclosing `self`.

## Declaration

```swift
nonisolated func windowDismissBehavior(_ behavior: WindowInteractionBehavior) -> some View

```

## Parameters

- **behavior**: The dismiss behavior.

## Discussion

By default, the window dismiss functionality is determined by the scene, as well as any modifiers applied to it.

You can use this modifier to override the default behavior.

For example, you can create a welcome workflow window which disables the dismiss functionality:

```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("Welcome", id: "welcome") {
            WelcomeView()
                .windowDismissBehavior(.disabled)
        }
    }
}
```

## Managing window behavior

- **WindowManagerRole**: Options for defining how a scene’s windows behave when used within a managed window context, such as full screen mode and Stage Manager.
- **windowManagerRole(_:)**: Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.
- **WindowInteractionBehavior**: Options for enabling and disabling window interaction behaviors.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowMinimizeBehavior(_:)**: Configures the minimize functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.
- **windowBackgroundDragBehavior(_:)**: Configures the behavior of dragging a window by its background.

