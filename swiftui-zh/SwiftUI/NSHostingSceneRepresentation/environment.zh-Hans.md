---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingSceneRepresentation/environment
抓取时间： 2025-12-03T06:57:50Z
---

# 环境

**实例属性**

由 `self` 表示的任何场景的环境。

## 声明

```swift
@MainActor var environment: EnvironmentValues { get }
```

## 讨论

使用环境值以编程方式显示场景窗口。

例如，当选择菜单项时，您可以使用 `Settings` 显示`Settings` 场景的窗口：

```swift
let settingsScene = NSHostingSceneRepresentation {
    Settings {
        SettingsView()
    }
}

@IBAction func showAppSettings(_ sender: NSMenuItem) {
    settingsScene.environment.openSettings()
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSceneRepresentation/environment
crawled: 2025-12-03T06:57:50Z
---

# environment

**Instance Property**

The environment for any scene(s) being represented by `self`.

## Declaration

```swift
@MainActor var environment: EnvironmentValues { get }
```

## Discussion

Use the environment values to programmatically present a scene’s window.

For example, you can present the window for a `Settings` scene using `OpenSettingsAction` when a menu item is selected:

```swift
let settingsScene = NSHostingSceneRepresentation {
    Settings {
        SettingsView()
    }
}

@IBAction func showAppSettings(_ sender: NSMenuItem) {
    settingsScene.environment.openSettings()
}
```

