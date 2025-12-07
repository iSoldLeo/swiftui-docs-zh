--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowBackgroundDragBehavior(_:)

抓取时间：2025-12-02T17:21:37Z

---

# windowBackgroundDragBehavior(_:)

**实例方法**

配置窗口通过其背景拖动的行为。

## 声明

```swift
nonisolated func windowBackgroundDragBehavior(_ behavior: WindowInteractionBehavior) -> some Scene

```

## 参数

- **behavior**：已修改窗口通过其背景拖动的行为。

## 返回值

已配置为通过其背景拖动的场景。

## 说明

默认情况下，或者当您应用 [automatic](../WindowInteractionBehavior/automatic.zh-Hans.md) 行为时，系统将根据已修改场景的配置确定最合适的行为。

您可以使用此修饰符来覆盖默认行为。例如，要始终允许按背景拖动窗口：

```swift
struct MyApp: App {
    var body: some Scene {
        Window("About MyApp", id: "about") {
            AboutView()
        }
        .windowBackgroundDragBehavior(.enabled)
    }
}
```

如果您希望允许用户按特定视图拖动窗口，而不是（或除了）按背景拖动窗口，请使用 [WindowDragGesture](../WindowDragGesture.zh-Hans.md)。

应用 [enabled](../WindowInteractionBehavior/enabled.zh-Hans.md) 行为相当于将 [WindowDragGesture](../WindowDragGesture.zh-Hans.md) 添加到窗口的背景视图。

## 管理窗口行为

- **WindowManagerRole**：用于定义场景窗口在受管窗口上下文（例如全屏模式和舞台管理器）中使用时的行为选项。

- **windowManagerRole(_:)**：配置从 `self` 派生的窗口在参与受管窗口上下文（例如全屏或舞台管理器）时的角色。

- **WindowInteractionBehavior**：启用和禁用窗口交互行为的选项。

- **windowDismissBehavior(_:)**：配置包含 `self` 的窗口的关闭功能。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowMinimizeBehavior(_:)**：配置包含 `self` 的窗口的最小化功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowBackgroundDragBehavior(_:)
crawled: 2025-12-02T17:21:37Z
---

# windowBackgroundDragBehavior(_:)

**Instance Method**

Configures the behavior of dragging a window by its background.

## Declaration

```swift
nonisolated func windowBackgroundDragBehavior(_ behavior: WindowInteractionBehavior) -> some Scene

```

## Parameters

- **behavior**: The behavior of dragging the modified window by its background.

## Return Value

A scene configured with the specified behavior of dragging it by its background background.

## Discussion

By default, or when you apply the [automatic](../WindowInteractionBehavior/automatic.zh-Hans.md) behavior, the system will determine the best suitable behavior based on the configuration of the modified scene.

You can use this modifier to override the default behavior. For example, to always enable dragging a window by its background:

```swift
struct MyApp: App {
    var body: some Scene {
        Window("About MyApp", id: "about") {
            AboutView()
        }
        .windowBackgroundDragBehavior(.enabled)
    }
}
```

If you want to let your users drag your window by a specific view instead of (or in addition to) letting them drag it by its background, use [WindowDragGesture](../WindowDragGesture.zh-Hans.md).

Applying the [enabled](../WindowInteractionBehavior/enabled.zh-Hans.md) behavior is equivalent to adding a [WindowDragGesture](../WindowDragGesture.zh-Hans.md) to the window’s background view.

## Managing window behavior

- **WindowManagerRole**: Options for defining how a scene’s windows behave when used within a managed window context, such as full screen mode and Stage Manager.
- **windowManagerRole(_:)**: Configures the role for windows derived from `self` when participating in a managed window context, such as full screen or Stage Manager.
- **WindowInteractionBehavior**: Options for enabling and disabling window interaction behaviors.
- **windowDismissBehavior(_:)**: Configures the dismiss functionality for the window enclosing `self`.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowMinimizeBehavior(_:)**: Configures the minimize functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.

