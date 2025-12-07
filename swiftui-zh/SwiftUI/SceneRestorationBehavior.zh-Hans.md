---
来源： https://developer.apple.com/documentation/SwiftUI/SceneRestorationBehavior
抓取时间： 2025-12-02T17:21:29Z
---

# 场景还原行为

**Structure**

场景的还原行为。

## 声明

```swift
struct SceneRestorationBehavior
```

## 概览

使用[restorationBehavior(_:)](scene/restorationBehavior.zh-Hans.md) 场景修饰符可将该类型的值应用到您在[App](App.zh-Hans.md) 声明中定义的[Scene](Scene.zh-Hans.md)。您指定的值将决定系统如何从应用程序的上一次运行中还原窗口。

例如，您可能有一个场景不希望在启动时还原：

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

## 类型属性

- **automatic**：自动行为。场景的窗口将按照底层平台的定义恢复。
- **disabled**：自动行为：禁用行为。不会恢复场景的窗口。

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。
- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。
- **restorationBehavior(_:)**：设置此场景的还原行为。
- **SceneLaunchBehavior**：场景的启动行为。
- **persistentSystemOverlays(_:)**：场景的启动行为：设置覆盖应用程序的非临时系统视图的首选可见性。
- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。
- **WindowToolbarFullScreenVisibility**：配置窗口进入全屏模式时窗口工具栏的可见性：窗口工具栏在全屏模式下的可见性。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SceneRestorationBehavior
crawled: 2025-12-02T17:21:29Z
---

# SceneRestorationBehavior

**Structure**

The restoration behavior for a scene.

## Declaration

```swift
struct SceneRestorationBehavior
```

## Overview

Use the [restorationBehavior(_:)](scene/restorationBehavior.zh-Hans.md) scene modifier to apply a value of this type to a [Scene](Scene.zh-Hans.md) you define in your [App](App.zh-Hans.md) declaration. The value you specify determines how the system will restore windows from a previous run of your application.

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

## Type Properties

- **automatic**: The automatic behavior. The scene’s windows will be restored as defined by the underlying platform.
- **disabled**: The disabled behavior. The scene’s windows will not be restored.

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

## Conforms To

- Sendable
- SendableMetatype

