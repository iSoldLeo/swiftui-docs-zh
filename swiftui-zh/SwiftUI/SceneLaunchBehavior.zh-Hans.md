---
来源： https://developer.apple.com/documentation/SwiftUI/SceneLaunchBehavior
抓取时间： 2025-12-02T17:21:28Z
---

# 场景启动行为

**Structure**

场景的启动行为。

## 声明

```swift
struct SceneLaunchBehavior
```

## 概览

使用[defaultLaunchBehavior(_:)](scene/defaultLaunchBehavior.zh-Hans.md)修饰符将此类型的值应用到您在[App](App.zh-Hans.md)中指定的[Scene](Scene.zh-Hans.md)。您指定的值将决定在启动应用程序时，如果没有任何先前恢复的场景，系统将如何显示场景。

例如，您可能希望在应用程序启动时显示一个欢迎窗口，而此时并没有恢复以前的文档窗口：

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

## 类型属性

- **automatic**：自动行为。
- **presented**：呈现行为。在没有任何先前还原的场景的情况下，场景将自动呈现。
- **suppressed**：抑制行为。在没有任何先前还原的场景的情况下，场景将不会呈现。

## 配置窗口可见性

- **WindowVisibilityToggle**：用于切换窗口可见性的专用按钮。
- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。
- **restorationBehavior(_:)**：设置此场景的还原行为。
- **SceneRestorationBehavior**：场景的还原行为。
- **persistentSystemOverlays(_:)**：设置覆盖应用程序的非暂态系统视图的首选可见性。
- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。
- **WindowToolbarFullScreenVisibility**：配置窗口进入全屏模式时窗口工具栏的可见性：窗口工具栏在全屏模式下的可见性。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SceneLaunchBehavior
crawled: 2025-12-02T17:21:28Z
---

# SceneLaunchBehavior

**Structure**

The launch behavior for a scene.

## Declaration

```swift
struct SceneLaunchBehavior
```

## Overview

Use the [defaultLaunchBehavior(_:)](scene/defaultLaunchBehavior.zh-Hans.md) modifier to apply a value of this type to a [Scene](Scene.zh-Hans.md) you specify in your [App](App.zh-Hans.md). The value you specify determines how the system will present the scene in the absense of any previously restored scenes on launch of your application.

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

## Type Properties

- **automatic**: The automatic behavior.
- **presented**: The presented behavior. The scene will present itself in the absence of any previously restored scenes.
- **suppressed**: The suppressed behavior. The scene will not present itself in the absence of any previously restored scenes.

## Configuring window visibility

- **WindowVisibilityToggle**: A specialized button for toggling the visibility of a window.
- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

## Conforms To

- Sendable
- SendableMetatype

