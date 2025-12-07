--- 来源：https://developer.apple.com/documentation/SwiftUI/View/windowToolbarFullScreenVisibility(_:)

抓取时间：2025-11-30T21:06:34Z

---

# windowToolbarFullScreenVisibility(_:)

**实例方法**

配置窗口进入全屏模式时窗口工具栏的可见性。

## 声明

```swift
nonisolated func windowToolbarFullScreenVisibility(_ visibility: WindowToolbarFullScreenVisibility) -> some View

```

## 参数

- **visibility**：窗口工具栏在全屏模式下的可见性。

## 说明

默认情况下，窗口工具栏会显示在屏幕顶部，位于窗口内容上方。

您可以使用此修饰符来覆盖默认行为。

例如，您可以指定窗口工具栏默认隐藏，仅当鼠标移入菜单栏区域时才显示：

```swift
struct RootView: View {
    var body: some View {
        ContentView()
            .toolbar {
                ...
            }
            .windowToolbarFullScreenVisibility(.onHover)
    }
}
```

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。

- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。

- **restorationBehavior(_:)**：设置此场景的恢复行为。

- **SceneLaunchBehavior**：场景的启动行为。

- **SceneRestorationBehavior**：场景的恢复行为。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **WindowToolbarFullScreenVisibility**：窗口工具栏在全屏模式下的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/windowToolbarFullScreenVisibility(_:)
crawled: 2025-11-30T21:06:34Z
---

# windowToolbarFullScreenVisibility(_:)

**Instance Method**

Configures the visibility of the window toolbar when the window enters full screen mode.

## Declaration

```swift
nonisolated func windowToolbarFullScreenVisibility(_ visibility: WindowToolbarFullScreenVisibility) -> some View

```

## Parameters

- **visibility**: The visibility to use for the window toolbar in full screen mode.

## Discussion

By default, the window toolbar will show at the top of the display, above the window’s contents.

You can use this modifier to override the default behavior.

For example, you can specify that the window toolbar should be hidden by default, and only show once the mouse moves into the area occupied by the menu bar:

```swift
struct RootView: View {
    var body: some View {
        ContentView()
            .toolbar {
                ...
            }
            .windowToolbarFullScreenVisibility(.onHover)
    }
}
```

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

