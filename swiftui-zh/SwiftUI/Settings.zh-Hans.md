--- 来源：https://developer.apple.com/documentation/SwiftUI/Settings

抓取时间：2025-12-02T17:20:52Z

---

# 设置

**Structure**

一个用于查看和修改应用设置的界面。

## 声明

```swift
struct Settings<Content> where Content : View
```

## 概述

使用设置场景可以让 SwiftUI 管理应用设置的控件视图。当您使用 [App](App.zh-Hans.md) 协议声明应用时，可以使用此场景。当您使用 [App](App.zh-Hans.md) 声明支持多个平台时，请仅在 macOS 上编译设置场景：

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
```

在 [App](App.zh-Hans.md) 声明中将视图作为参数传递给设置场景，会导致 SwiftUI 启用应用程序的“设置”菜单项。当用户从应用程序菜单或使用等效的键盘快捷键选择“设置”项时，SwiftUI 会管理设置视图的显示和隐藏：

设置视图的内容是一些控件，它们会修改绑定到 SwiftUI 使用 [AppStorage](AppStorage.zh-Hans.md) 属性包装器管理的 [doc://com.apple.documentation/documentation/Foundation/UserDefaults] 值的绑定：

```swift
struct GeneralSettingsView: View {
    @AppStorage("showPreview") private var showPreview = true
    @AppStorage("fontSize") private var fontSize = 12.0

    var body: some View {
        Form {
            Toggle("Show Previews", isOn: $showPreview)
            Slider(value: $fontSize, in: 9...96) {
                Text("Font Size (\(fontSize, specifier: "%.0f") pts)")
            }
        }
    }
}
```

您可以将设置定义在单个视图中，也可以使用 [TabView](TabView.zh-Hans.md) 将设置分组到不同的集合中：

```swift
struct SettingsView: View {
    var body: some View {
        TabView {
            Tab("General", systemImage: "gear") {
                GeneralSettingsView()
            }
            Tab("Advanced", systemImage: "star") {
                AdvancedSettingsView()
            }
        }
        .scenePadding()
        .frame(maxWidth: 350, minHeight: 100)
    }
}
```

## 创建设置场景

- **init(content:)**：创建一个用于查看和修改应用程序首选项的界面的场景。

## 管理设置窗口

- **SettingsLink**：一个用于打开应用程序定义的设置场景的视图。

- **OpenSettingsAction**：用于呈现应用设置场景的操作。

- **openSettings**：存储在视图环境中的设置呈现操作。

## 符合以下规范

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/Settings
crawled: 2025-12-02T17:20:52Z
---

# Settings

**Structure**

A scene that presents an interface for viewing and modifying an app’s settings.

## Declaration

```swift
struct Settings<Content> where Content : View
```

## Overview

Use a settings scene to have SwiftUI manage views with controls for your app’s settings when you declare your app using the [App](App.zh-Hans.md) protocol. When you use an [App](App.zh-Hans.md) declaration for multiple platforms, compile the settings scene only in macOS:

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
```

Passing a view as the argument to a settings scene in the [App](App.zh-Hans.md) declaration causes SwiftUI to enable the app’s Settings menu item. SwiftUI manages displaying and removing the settings view when the user selects the Settings item from the application menu or the equivalent keyboard shortcut:



The contents of your settings view are controls that modify bindings to [doc://com.apple.documentation/documentation/Foundation/UserDefaults] values that SwiftUI manages using the [AppStorage](AppStorage.zh-Hans.md) property wrapper:

```swift
struct GeneralSettingsView: View {
    @AppStorage("showPreview") private var showPreview = true
    @AppStorage("fontSize") private var fontSize = 12.0

    var body: some View {
        Form {
            Toggle("Show Previews", isOn: $showPreview)
            Slider(value: $fontSize, in: 9...96) {
                Text("Font Size (\(fontSize, specifier: "%.0f") pts)")
            }
        }
    }
}
```

You can define your settings in a single view, or you can use a [TabView](TabView.zh-Hans.md) to group settings into different collections:

```swift
struct SettingsView: View {
    var body: some View {
        TabView {
            Tab("General", systemImage: "gear") {
                GeneralSettingsView()
            }
            Tab("Advanced", systemImage: "star") {
                AdvancedSettingsView()
            }
        }
        .scenePadding()
        .frame(maxWidth: 350, minHeight: 100)
    }
}
```



## Creating a settings scene

- **init(content:)**: Creates a scene that presents an interface for viewing and modifying an app’s preferences.

## Managing a settings window

- **SettingsLink**: A view that opens the Settings scene defined by an app.
- **OpenSettingsAction**: An action that presents the settings scene for an app.
- **openSettings**: A Settings presentation action stored in a view’s environment.

## Conforms To

- Scene

