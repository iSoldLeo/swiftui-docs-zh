--- 来源：https://developer.apple.com/documentation/SwiftUI/ScenePhase
抓取时间：2025-12-02T17:20:51Z

---

# ScenePhase

**Enumeration**

指示场景的运行状态。

## 声明

```swift
enum ScenePhase
```

## 概述

系统会根据场景的运行状态，将应用程序的 [Scene](Scene.zh-Hans.md) 实例在不同阶段之间切换。您可以在阶段切换时触发操作。通过观察 [Environment](Environment.zh-Hans.md) 中的 [scenePhase](EnvironmentValues/scenePhase.zh-Hans.md) 值来读取当前阶段：

```swift
@Environment(\.scenePhase) private var scenePhase
```

如何解读该值取决于其读取位置。如果从 [View](View.zh-Hans.md) 实例内部读取阶段值，则会获得一个反映包含该视图的场景阶段的值。以下示例使用 [onChange(of:initial:_:)-8wgw9](View/onChange_of_initial___-8wgw9.zh-Hans.md) 方法，在包含该视图的场景进入 [active](ScenePhase/active.zh-Hans.md) 阶段时启用计时器，并在进入任何其他阶段时禁用计时器：

```swift
struct MyView: View {
    @ObservedObject var model: DataModel
    @Environment(\.scenePhase) private var scenePhase

    var body: some View {
        TimerView()
            .onChange(of: scenePhase) {
                model.isTimerRunning = (scenePhase == .active)
            }
    }
}
```

如果从 [App](App.zh-Hans.md) 实例内部读取阶段值，则会获得一个反映应用程序中所有场景阶段的聚合值。如果任何场景处于活动状态，则应用程序报告值为 [active](ScenePhase/active.zh-Hans.md)；如果没有场景处于活动状态，则报告值为 [inactive](ScenePhase/inactive.zh-Hans.md)。这包括从单个场景声明创建的多个场景实例；例如，从 [WindowGroup](WindowGroup.zh-Hans.md) 创建。当应用进入 [background](ScenePhase/background.zh-Hans.md) 阶段时，预计应用很快就会终止。您可以利用这个机会释放所有资源：

```swift
@main
struct MyApp: App {
    @Environment(\.scenePhase) private var scenePhase

    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
        .onChange(of: scenePhase) {
            if scenePhase == .background {
                // Perform cleanup when all scenes within
                // MyApp go to the background.
            }
        }
    }
}
```

## 获取场景阶段

- **ScenePhase.active**：场景处于前台且可交互。

- **ScenePhase.inactive**：场景处于前台，但应暂停运行。

- **ScenePhase.background**：场景当前在用户界面中不可见。

## 监控场景生命周期

- **scenePhase**：场景的当前阶段。

## 符合以下协议：

- Comparable

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ScenePhase
crawled: 2025-12-02T17:20:51Z
---

# ScenePhase

**Enumeration**

An indication of a scene’s operational state.

## Declaration

```swift
enum ScenePhase
```

## Overview

The system moves your app’s [Scene](Scene.zh-Hans.md) instances through phases that reflect a scene’s operational state. You can trigger actions when the phase changes. Read the current phase by observing the [scenePhase](EnvironmentValues/scenePhase.zh-Hans.md) value in the [Environment](Environment.zh-Hans.md):

```swift
@Environment(\.scenePhase) private var scenePhase
```

How you interpret the value depends on where it’s read from. If you read the phase from inside a [View](View.zh-Hans.md) instance, you obtain a value that reflects the phase of the scene that contains the view. The following example uses the [onChange(of:initial:_:)-8wgw9](View/onChange_of_initial___-8wgw9.zh-Hans.md) method to enable a timer whenever the enclosing scene enters the [active](ScenePhase/active.zh-Hans.md) phase and disable the timer when entering any other phase:

```swift
struct MyView: View {
    @ObservedObject var model: DataModel
    @Environment(\.scenePhase) private var scenePhase

    var body: some View {
        TimerView()
            .onChange(of: scenePhase) {
                model.isTimerRunning = (scenePhase == .active)
            }
    }
}
```

If you read the phase from within an [App](App.zh-Hans.md) instance, you obtain an aggregate value that reflects the phases of all the scenes in your app. The app reports a value of [active](ScenePhase/active.zh-Hans.md) if any scene is active, or a value of [inactive](ScenePhase/inactive.zh-Hans.md) when no scenes are active. This includes multiple scene instances created from a single scene declaration; for example, from a [WindowGroup](WindowGroup.zh-Hans.md). When an app enters the [background](ScenePhase/background.zh-Hans.md) phase, expect the app to terminate soon after. You can use that opportunity to free any resources:

```swift
@main
struct MyApp: App {
    @Environment(\.scenePhase) private var scenePhase

    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
        .onChange(of: scenePhase) {
            if scenePhase == .background {
                // Perform cleanup when all scenes within
                // MyApp go to the background.
            }
        }
    }
}
```

## Getting scene phases

- **ScenePhase.active**: The scene is in the foreground and interactive.
- **ScenePhase.inactive**: The scene is in the foreground but should pause its work.
- **ScenePhase.background**: The scene isn’t currently visible in the UI.

## Monitoring scene life cycle

- **scenePhase**: The current phase of the scene.

## Conforms To

- Comparable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

