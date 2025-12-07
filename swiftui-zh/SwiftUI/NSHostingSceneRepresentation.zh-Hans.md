---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingSceneRepresentation
抓取时间： 2025-12-02T17:44:44Z
---

# NSHostingSceneRepresentation

**Class**

可托管并呈现 SwiftUI 场景的 AppKit 类型

## 声明

```swift
@MainActor class NSHostingSceneRepresentation<Content> where Content : Scene
```

## 概览

将此类型的实例与 `NSApplication.addSceneRepresentation(_:)` 搭配使用，可在使用 AppKit 应用程序生命周期的应用程序中包含 SwiftUI 场景功能。

例如，您可以在应用程序中添加`Settings` 场景，并在选择相应菜单项时显示该场景：

```swift
import AppKit
import SwiftUI

@main
class ApplicationDelegate: NSApplicationDelegate {
    let settingsScene = NSHostingSceneRepresentation {
        Settings {
            SettingsView()
        }
    }

    func applicationWillFinishLaunching(_ notification: Notification) {
        NSApplication.shared.addSceneRepresentation(settingsScene)
    }

    @IBAction func showAppSettings(_ sender: NSMenuItem) {
        settingsScene.environment.openSettings()
    }
}
```

## 初始化程序

- **init(rootScene:)**：为指定场景创建新的托管场景表示。

## 实例属性

- **environment**：`self`所代表的任何场景的环境。

## 在 AppKit 中显示 SwiftUI 视图

- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **NSHostingController**：托管 SwiftUI 视图层次结构的 AppKit 视图控制器。
- **NSHostingView**：托管 SwiftUI 视图层次结构的 AppKit 视图。
- **NSHostingMenu**：包含由 SwiftUI 视图定义的菜单项的 AppKit 菜单。
- **NSHostingSizingOptions**：关于托管视图和控制器如何将其内容的大小反映到自动布局约束中的选项。
- **NSHostingSceneBridgingOptions**：有关托管视图和控制器如何管理相关窗口的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSceneRepresentation
crawled: 2025-12-02T17:44:44Z
---

# NSHostingSceneRepresentation

**Class**

An AppKit type that hosts and can present SwiftUI scenes

## Declaration

```swift
@MainActor class NSHostingSceneRepresentation<Content> where Content : Scene
```

## Overview

Use instances of this type with `NSApplication.addSceneRepresentation(_:)` to include SwiftUI scene functionality in an app which uses the AppKit app lifecycle.

For example, you can add a `Settings` scene to your app and present it when the corresponding menu item is selected:

```swift
import AppKit
import SwiftUI

@main
class ApplicationDelegate: NSApplicationDelegate {
    let settingsScene = NSHostingSceneRepresentation {
        Settings {
            SettingsView()
        }
    }

    func applicationWillFinishLaunching(_ notification: Notification) {
        NSApplication.shared.addSceneRepresentation(settingsScene)
    }

    @IBAction func showAppSettings(_ sender: NSMenuItem) {
        settingsScene.environment.openSettings()
    }
}
```

## Initializers

- **init(rootScene:)**: Creates a new hosting scene representation for the specified scene(s).

## Instance Properties

- **environment**: The environment for any scene(s) being represented by `self`.

## Displaying SwiftUI views in AppKit

- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **NSHostingController**: An AppKit view controller that hosts SwiftUI view hierarchy.
- **NSHostingView**: An AppKit view that hosts a SwiftUI view hierarchy.
- **NSHostingMenu**: An AppKit menu with menu items that are defined by a SwiftUI View.
- **NSHostingSizingOptions**: Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.
- **NSHostingSceneBridgingOptions**: Options for how hosting views and controllers manage aspects of the associated window.

