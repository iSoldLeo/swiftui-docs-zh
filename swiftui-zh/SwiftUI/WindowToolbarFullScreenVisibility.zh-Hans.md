---
来源： https://developer.apple.com/documentation/SwiftUI/WindowToolbarFullScreenVisibility
抓取时间： 2025-12-02T17:21:31Z
---

# WindowToolbarFullScreenVisibility

**Structure**

窗口工具栏在全屏模式下的可见性。

## 声明

```swift
struct WindowToolbarFullScreenVisibility
```

## 概览

将此类型的值与[windowToolbarFullScreenVisibility(_:)](View/windowToolbarFullScreenVisibility.zh-Hans.md) 修改器结合使用，可配置窗口进入全屏模式时窗口工具栏的显示方式。

例如，可以指定窗口工具栏默认为隐藏，只有当鼠标移动到菜单栏所占区域时才显示：

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

## 类型属性

- **automatic**：窗口工具栏可见性将由系统默认行为定义。
- **onHover**：在全屏模式下默认隐藏窗口工具栏。当鼠标移动到菜单栏所占区域时，它将显示出来。
- **visible**：首选在全屏模式下显示窗口工具栏。

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。
- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。
- **restorationBehavior(_:)**：设置此场景的默认启动行为：设置此场景的还原行为。
- **SceneLaunchBehavior**：场景的启动行为。
- **SceneRestorationBehavior**：场景的启动行为：场景的恢复行为。
- **persistentSystemOverlays(_:)**：场景的恢复行为：设置覆盖应用程序的非临时系统视图的首选可见性。
- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WindowToolbarFullScreenVisibility
crawled: 2025-12-02T17:21:31Z
---

# WindowToolbarFullScreenVisibility

**Structure**

The visibility of the window toolbar with respect to full screen mode.

## Declaration

```swift
struct WindowToolbarFullScreenVisibility
```

## Overview

Use values of this type in conjunction with the [windowToolbarFullScreenVisibility(_:)](View/windowToolbarFullScreenVisibility.zh-Hans.md) modifier to configure how the window toolbar displays itself when the window enters full screen mode.

For example, you can specify that the window toolbar should be hidden by default, and only show when the mouse moves into the area occupied by the menu bar:

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

## Type Properties

- **automatic**: The window toolbar visibility will be defined by the system default behavior.
- **onHover**: Hide the window toolbar in full screen mode by default. It will reveal itself when the mouse moves into the area occupied by the menu bar.
- **visible**: Prefer to show window toolbar when the window is in full screen mode.

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.

## Conforms To

- Sendable
- SendableMetatype

