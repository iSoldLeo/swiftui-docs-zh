---
来源： https://developer.apple.com/documentation/SwiftUI/OpenSettingsAction
抓取时间： 2025-12-02T17:20:53Z
---

# OpenSettingsAction

**Structure**

显示应用程序设置场景的操作。

## 声明

```swift
@MainActor @preconcurrency struct OpenSettingsAction
```

## 概览

使用[openSettings](EnvironmentValues/openSettings.zh-Hans.md) 环境值为给定的[Environment](Environment.zh-Hans.md) 获取此结构的实例。然后调用该实例打开一个窗口。我们直接调用该实例是因为它定义了一个 [callAsFunction()](OpenSettingsAction/callAsFunction.zh-Hans.md) 方法，当我们调用该实例时，Swift 会调用该方法。

例如，您可以定义一个按钮来打开特定选项卡的设置窗口：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        #if os(macOS)
        Settings {
            SettingsView()
        }
        #endif
    }
}

struct SettingsView: View {
    @AppStorage("selectedSettingsTab")
    private var selectedSettingsTab = SettingsTab.general

    var body: some View {
        TabView(selection: $selectedSettingsTab) {
            GeneralSettings()
            AdvancedSettings()
        }
    }
}

struct AdvancedSettingsButton: View {
    @AppStorage("selectedSettingsTab")
    private var selectedSettingsTab = SettingsTab.general

    @Environment(\.openSettings) private var openSettings

    var body: some View {
        Button("Open Advanced Settings…") {
            selectedSettingsTab = .advanced
            openSettings()
        }
    }
}

enum SettingsTab: Int {
    case general
    case advanced
}
```

### 实例方法

- **callAsFunction()**：打开与此应用程序定义的 [Settings](Settings.zh-Hans.md) 场景相关的窗口（如果存在）。

## 管理设置窗口

- **Settings**：显示用于查看和修改应用程序设置的界面的场景。
- **SettingsLink**：打开应用程序定义的 "设置 "场景的视图。
- **openSettings**：存储在视图环境中的 "设置 "演示操作。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/OpenSettingsAction
crawled: 2025-12-02T17:20:53Z
---

# OpenSettingsAction

**Structure**

An action that presents the settings scene for an app.

## Declaration

```swift
@MainActor @preconcurrency struct OpenSettingsAction
```

## Overview

Use the [openSettings](EnvironmentValues/openSettings.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to open a window. You call the instance directly because it defines a [callAsFunction()](OpenSettingsAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can define a button that opens the settings window to a particular tab:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        #if os(macOS)
        Settings {
            SettingsView()
        }
        #endif
    }
}

struct SettingsView: View {
    @AppStorage("selectedSettingsTab")
    private var selectedSettingsTab = SettingsTab.general

    var body: some View {
        TabView(selection: $selectedSettingsTab) {
            GeneralSettings()
            AdvancedSettings()
        }
    }
}

struct AdvancedSettingsButton: View {
    @AppStorage("selectedSettingsTab")
    private var selectedSettingsTab = SettingsTab.general

    @Environment(\.openSettings) private var openSettings

    var body: some View {
        Button("Open Advanced Settings…") {
            selectedSettingsTab = .advanced
            openSettings()
        }
    }
}

enum SettingsTab: Int {
    case general
    case advanced
}
```

## Instance Methods

- **callAsFunction()**: Opens the window associated to the [Settings](Settings.zh-Hans.md) scene defined by this app, if one exists.

## Managing a settings window

- **Settings**: A scene that presents an interface for viewing and modifying an app’s settings.
- **SettingsLink**: A view that opens the Settings scene defined by an app.
- **openSettings**: A Settings presentation action stored in a view’s environment.

## Conforms To

- Sendable
- SendableMetatype

