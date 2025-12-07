--- 来源：https://developer.apple.com/documentation/SwiftUI/View/windowMinimizeBehavior(_:)

抓取时间：2025-11-30T21:06:39Z

---

# windowMinimizeBehavior(_:)

**实例方法**

配置包含 `self` 的窗口的最小化功能。

## 声明

```swift
nonisolated func windowMinimizeBehavior(_ behavior: WindowInteractionBehavior) -> some View

```

## 参数

- **behavior**：调整大小的行为。

## 说明

在 macOS 上，支持最小化的窗口会在单击最小化按钮或选择相应的菜单项时移动到 Dock 栏。

默认情况下，窗口的最小化功能由场景及其应用的任何修饰符决定。

您可以使用此修饰符来覆盖默认行为。

例如，您可以创建一个自定义的“关于”窗口，禁用最小化功能：

```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("About MyApp", id: "about") {
            AboutView()
                .windowResizeBehavior(.disabled)
                .windowMinimizeBehavior(.disabled)
        }
        .windowResizability(.contentSize)
    }
}
```

## 管理窗口行为

- **WindowManagerRole**：用于定义场景窗口在受管窗口上下文（例如全屏模式和舞台管理器）中使用时的行为选项。

- **windowManagerRole(_:)**：配置从 `self` 派生的窗口在参与受管窗口上下文（例如全屏或舞台管理器）时的角色。

- **WindowInteractionBehavior**：用于启用和禁用窗口交互行为的选项。

- **windowDismissBehavior(_:)**：配置包含 `self` 的窗口的关闭功能。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。

- **windowBackgroundDragBehavior(_:)**：配置拖动窗口背景的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/windowMinimizeBehavior(_:)
crawled: 2025-11-30T21:06:39Z
---

# windowMinimizeBehavior(_:)

**Instance Method**

Configures the minimize functionality for the window enclosing `self`.

## Declaration

```swift
nonisolated func windowMinimizeBehavior(_ behavior: WindowInteractionBehavior) -> some View

```

## Parameters

- **behavior**: The resize behavior.

## Discussion

On macOS, windows which support being minimized will move into the Dock when the minimize button is clicked, or the corresponding menu item is selected.

By default, the window minimize functionality is determined by the scene, as well as any modifiers applied to it.

You can use this modifier to override the default behavior.

For example, you can create a custom “About” window which disables the minimize functionality:

```swift
struct MyApp: App {
    var body: some Scene {
        ...
        Window("About MyApp", id: "about") {
            AboutView()
                .windowResizeBehavior(.disabled)
                .windowMinimizeBehavior(.disabled)
        }
        .windowResizability(.contentSize)
    }
}
```

## Managing window behavior

- **WindowManagerRole**: Options for defining how a scene’s windows behave when used within a managed window context, such as full screen mode and Stage Manager.
- **windowManagerRole(_:)**: Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.
- **WindowInteractionBehavior**: Options for enabling and disabling window interaction behaviors.
- **windowDismissBehavior(_:)**: Configures the dismiss functionality for the window enclosing `self`.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.
- **windowBackgroundDragBehavior(_:)**: Configures the behavior of dragging a window by its background.

