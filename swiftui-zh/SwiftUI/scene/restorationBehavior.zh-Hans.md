--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/restorationBehavior(_:)

抓取时间：2025-11-30T21:06:31Z

---

# restorationBehavior(_:)

**实例方法**

设置此场景的恢复行为。

## 声明

```swift
nonisolated func restorationBehavior(_ behavior: SceneRestorationBehavior) -> some Scene

```

## 说明

使用此场景修改器，可将此类型的值应用于您在 [App](../App.zh-Hans.md) 声明中定义的 [Scene](../Scene.zh-Hans.md)。您指定的值决定了系统如何从应用程序的先前运行中恢复窗口。

例如，您可能有一个场景不希望在启动时恢复：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        Window(id: "network-test", "Network Connection Test") {
            NetworkTestView()
        }
        .restorationBehavior(.disabled)
    }
}
```

如果您不应用此修饰符，则所有场景的默认值为 [automatic](../SceneRestorationBehavior/automatic.zh-Hans.md)。采用此策略，场景将根据平台的默认行为自行恢复。

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。

- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。

- **SceneLaunchBehavior**：场景的启动行为。

- **SceneRestorationBehavior**：场景的恢复行为。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。

- **WindowToolbarFullScreenVisibility**：窗口工具栏在全屏模式下的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/restorationBehavior(_:)
crawled: 2025-11-30T21:06:31Z
---

# restorationBehavior(_:)

**Instance Method**

Sets the restoration behavior for this scene.

## Declaration

```swift
nonisolated func restorationBehavior(_ behavior: SceneRestorationBehavior) -> some Scene

```

## Discussion

Use this scene modifier to apply a value of this type to a [Scene](../Scene.zh-Hans.md) you define in your [App](../App.zh-Hans.md) declaration. The value you specify determines how the system will restore windows from a previous run of your application.

For example, you may have a scene that you do not wish to be restored on launch:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        Window(id: "network-test", "Network Connection Test") {
            NetworkTestView()
        }
        .restorationBehavior(.disabled)
    }
}
```

The default value for all scenes if you do not apply the modifier is [automatic](../SceneRestorationBehavior/automatic.zh-Hans.md). With that strategy, scenes will restore themselves depending on the default behavior for the platform.

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

