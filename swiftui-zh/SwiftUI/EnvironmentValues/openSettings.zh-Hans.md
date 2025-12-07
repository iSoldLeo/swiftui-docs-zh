---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openSettings
抓取时间： 2025-12-02T17:20:54Z
---

# 打开设置

**实例属性**

存储在视图环境中的设置演示操作。

## 声明

```swift
var openSettings: OpenSettingsAction { get }
```

## 讨论

使用`openSettings` 环境值为给定的[OpenSettingsAction](../OpenSettingsAction.zh-Hans.md) 实例获取[Environment](../Environment.zh-Hans.md)。然后调用该实例打开一个窗口。我们直接调用该实例，因为它定义了一个 [callAsFunction()](../OpenSettingsAction/callAsFunction.zh-Hans.md) 方法，当我们调用该实例时，Swift 会调用该方法。

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

## 管理设置窗口

- **Settings**：显示用于查看和修改应用程序设置的界面的场景。
- **SettingsLink**：打开应用程序定义的 "设置 "场景的视图。
- **OpenSettingsAction**：显示应用程序设置场景的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openSettings
crawled: 2025-12-02T17:20:54Z
---

# openSettings

**Instance Property**

A Settings presentation action stored in a view’s environment.

## Declaration

```swift
var openSettings: OpenSettingsAction { get }
```

## Discussion

Use the `openSettings` environment value to get an [OpenSettingsAction](../OpenSettingsAction.zh-Hans.md) instance for a given [Environment](../Environment.zh-Hans.md). Then call the instance to open a window. You call the instance directly because it defines a [callAsFunction()](../OpenSettingsAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

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

## Managing a settings window

- **Settings**: A scene that presents an interface for viewing and modifying an app’s settings.
- **SettingsLink**: A view that opens the Settings scene defined by an app.
- **OpenSettingsAction**: An action that presents the settings scene for an app.

