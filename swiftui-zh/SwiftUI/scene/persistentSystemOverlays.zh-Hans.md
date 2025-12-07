--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/persistentSystemOverlays(_:)

抓取时间：2025-12-02T17:21:30Z

---

# persistentSystemOverlays(_:)

**实例方法**

设置覆盖在应用上的非瞬态系统视图的首选可见性。

## 声明

```swift
nonisolated func persistentSystemOverlays(_ preferredVisibility: Visibility) -> some Scene

```

## 说明

使用此修饰符可以影响应用中系统覆盖层的外观。其行为因平台而异。

在 iOS 中，以下示例会隐藏所有持久系统覆盖层。在 visionOS 2 及更高版本中，如果场景通过 SharePlay 共享，或者根本没有共享，则 SharePlay 指示器会隐藏。在屏幕共享期间，指示器始终保持可见。将可见性设置为 `hidden` 时，如果没有用户的特定意图，则主屏幕指示器不会显示。对于 [WindowGroup](../WindowGroup.zh-Hans.md)，此修饰符会影响窗口边框的可见性。对于 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md)，它会影响主屏幕指示器。

```swift
struct ImmersiveView: View {
    var body: some View {
        Text("Maximum immersion")
            .persistentSystemOverlays(.hidden)
    }
}
```

受影响的非瞬态系统视图包括但不限于：

- 主屏幕指示器。

- SharePlay 指示器。

- iPad 上的多任务控制按钮和画中画功能。

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。

- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。

- **restorationBehavior(_:)**：设置此场景的恢复行为。

- **SceneLaunchBehavior**：场景的启动行为。

- **SceneRestorationBehavior**：场景的恢复行为。

- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。

- **WindowToolbarFullScreenVisibility**：窗口工具栏相对于全屏模式的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/persistentSystemOverlays(_:)
crawled: 2025-12-02T17:21:30Z
---

# persistentSystemOverlays(_:)

**Instance Method**

Sets the preferred visibility of the non-transient system views overlaying the app.

## Declaration

```swift
nonisolated func persistentSystemOverlays(_ preferredVisibility: Visibility) -> some Scene

```

## Discussion

Use this modifier to influence the appearance of system overlays in your app. The behavior varies by platform.

In iOS, the following example hides every persistent system overlay. In visionOS 2 and later, the SharePlay Indicator hides if the scene is shared through SharePlay, or not shared at all. During screen sharing, the indicator always remains visible. The Home indicator doesn’t appear without specific user intent when you set visibility to `hidden`. For a [WindowGroup](../WindowGroup.zh-Hans.md), the modifier affects the visibility of the window chrome. For an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md), it affects the Home indicator.

```swift
struct ImmersiveView: View {
    var body: some View {
        Text("Maximum immersion")
            .persistentSystemOverlays(.hidden)
    }
}
```



Affected non-transient system views can include, but are not limited to:

- The Home indicator.
- The SharePlay indicator.
- The Multitasking Controls button and Picture in Picture on iPad.

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

