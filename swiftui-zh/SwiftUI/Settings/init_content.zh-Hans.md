---
来源： https://developer.apple.com/documentation/SwiftUI/Settings/init(内容：)
抓取时间： 2025-12-03T05:31:16Z
---

# init(content:)

**Initializer**

创建一个场景，提供查看和修改应用程序首选项的界面。

## 声明

```swift
init(@ViewBuilder content: () -> Content)
```

## 参数

- **content**：表示场景内容的视图。

## 讨论

当您使用 `Settings(content:)` 协议声明应用程序时，请使用 `Settings(content:)` 添加首选项场景。

下面的示例显示了添加到 SwiftUI 应用程序委托的设置场景的视图内容：

```swift
@main
struct MacSwiftUISnippets: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        #if os(macOS)
        Settings(content: {
            SettingsView()
        }
        #endif
    }
}
```

当您在多个平台上使用[App](../App.zh-Hans.md) 声明时，请仅在 macOS 中编译设置场景，如上例所示。


---
source: https://developer.apple.com/documentation/SwiftUI/Settings/init(content:)
crawled: 2025-12-03T05:31:16Z
---

# init(content:)

**Initializer**

Creates a scene that presents an interface for viewing and modifying an app’s preferences.

## Declaration

```swift
init(@ViewBuilder content: () -> Content)
```

## Parameters

- **content**: A view that represents the content of the scene.

## Discussion

Use `Settings(content:)` to add a preferences scene when you declare your app using the [App](../App.zh-Hans.md) protocol.

The example below shows the view content for the settings scene added to the SwiftUI app delegate:

```swift
@main
struct MacSwiftUISnippets: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        #if os(macOS)
        Settings(content: {
            SettingsView()
        }
        #endif
    }
}
```

When you use an [App](../App.zh-Hans.md) declaration for multiple platforms, compile the settings scene only in macOS, as shown in the example above.

