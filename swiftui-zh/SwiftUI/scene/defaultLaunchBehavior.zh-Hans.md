--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/defaultLaunchBehavior(_:)

抓取时间：2025-12-02T17:21:27Z

---

# defaultLaunchBehavior(_:)

**实例方法**

设置此场景的默认启动行为。

## 声明

```swift
nonisolated func defaultLaunchBehavior(_ behavior: SceneLaunchBehavior) -> some Scene

```

## 讨论

此行为可用于定义在应用程序启动时，如果没有预先保存任何状态，是否显示某个场景。

在不支持多窗口的平台上，此值将被忽略。

在 macOS 以外的平台上，必须至少有一个场景需要显示。如果没有定义要显示的场景，则会显示第一个场景，而不管此修饰符的值是多少。

在 macOS 上，此行为还用于确定点击正在运行且没有可见窗口的应用程序图标时显示的场景。

在 visionOS 上，系统可能会将上次关闭的场景置于后台，而不是将其关闭。因此，被抑制的行为还指定了在点击没有可见窗口的应用程序图标时不应显示该场景。

例如，您可能希望在应用程序启动时显示一个欢迎窗口，前提是没有恢复任何先前的文档窗口：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: MyDocument()) { configuration in
            DocumentEditor(configuration.$document)
        }

        Window("Welcome to My App", id: "welcome") {
            WelcomeView()
        }
        .defaultLaunchBehavior(.presented)
    }
}
```

如果您不应用此修饰符，则所有场景的默认值为 [automatic](../SceneLaunchBehavior/automatic.zh-Hans.md)。采用此策略，只有当场景是应用程序定义的第一个场景，且没有其他场景显示时，该场景才会显示。

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。

- **restorationBehavior(_:)**：设置此场景的恢复行为。

- **SceneLaunchBehavior**：场景的启动行为。

- **SceneRestorationBehavior**：场景的恢复行为。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。

- **WindowToolbarFullScreenVisibility**：窗口工具栏在全屏模式下的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/defaultLaunchBehavior(_:)
crawled: 2025-12-02T17:21:27Z
---

# defaultLaunchBehavior(_:)

**Instance Method**

Sets the default launch behavior for this scene.

## Declaration

```swift
nonisolated func defaultLaunchBehavior(_ behavior: SceneLaunchBehavior) -> some Scene

```

## Discussion

This behavior can be used to define if a scene is shown on application launch in the absence of any previously saved state.

On platforms that do not support multiple windows, this value is ignored.

On platforms other than macOS, there must be at least one scene that presents itself. If no scenes are defined to present, the first scene will be presented, regardless of the value provided to this modifier.



On macOS, this behavior will also be used to determine which scene is presented when clicking on the icon of a running application with no visible windows.

On visionOS, the system may background the last dismissed scene instead of closing it. Thus, the suppressed behavior additionally specifies that the scene should not be presented when tapping on the application icon with no visible windows.

For example, you may wish to present a welcome window on launch of your app when there are no previous document windows being restored:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: MyDocument()) { configuration in
            DocumentEditor(configuration.$document)
        }

        Window("Welcome to My App", id: "welcome") {
            WelcomeView()
        }
        .defaultLaunchBehavior(.presented)
    }
}
```

The default value for all scenes if you do not apply this modifier is [automatic](../SceneLaunchBehavior/automatic.zh-Hans.md). With that strategy, a scene will only present itself if it is the first scene defined by the app, and no other scenes have presented themselves.

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

