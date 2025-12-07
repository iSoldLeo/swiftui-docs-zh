---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportsMultipleWindows
抓取时间： 2025-12-02T17:21:06Z
---

# 支持多窗口

**实例属性**

布尔值，表示当前平台是否支持打开多个窗口。

## 声明

```swift
var supportsMultipleWindows: Bool { get }
```

## 讨论

从环境中读取此属性，以确定应用程序是否可以使用 [openWindow](openWindow.zh-Hans.md) 操作来打开新窗口：

```swift
struct NewMailViewerButton: View {
    @Environment(\.supportsMultipleWindows) private var supportsMultipleWindows
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open New Window") {
            openWindow(id: "mail-viewer")
        }
        .disabled(!supportsMultipleWindows)
    }
}
```

报告的值取决于平台和您配置应用程序的方式：

- 在 macOS 中，对于使用 SwiftUI 应用程序生命周期的任何应用程序，此属性都会返回 `true`。
- 在 iPadOS 中，对于使用 SwiftUI 应用程序生命周期并将信息属性列表键 [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UIApplicationSupportsMultipleScenes] 设为 `true`的任何应用程序，此属性都会返回`true`。
- 对于所有其他平台和配置，该值返回 `false`。

如果值为 false 并尝试打开窗口，SwiftUI 将忽略该操作并记录运行时错误。

## 打开窗口

- 呈现窗口和空间**：打开和关闭组成应用程序界面的场景。
- **openWindow**：存储在视图环境中的窗口呈现操作。
- **OpenWindowAction**：显示窗口的操作。
- **PushWindowAction**：打开所请求的窗口，以代替调用该操作的窗口的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/supportsMultipleWindows
crawled: 2025-12-02T17:21:06Z
---

# supportsMultipleWindows

**Instance Property**

A Boolean value that indicates whether the current platform supports opening multiple windows.

## Declaration

```swift
var supportsMultipleWindows: Bool { get }
```

## Discussion

Read this property from the environment to determine if your app can use the [openWindow](openWindow.zh-Hans.md) action to open new windows:

```swift
struct NewMailViewerButton: View {
    @Environment(\.supportsMultipleWindows) private var supportsMultipleWindows
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open New Window") {
            openWindow(id: "mail-viewer")
        }
        .disabled(!supportsMultipleWindows)
    }
}
```

The reported value depends on both the platform and how you configure your app:

- In macOS, this property returns `true` for any app that uses the SwiftUI app lifecycle.
- In iPadOS, this property returns `true` for any app that uses the SwiftUI app lifecycle and has the Information Property List key [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UIApplicationSupportsMultipleScenes] set to `true`.
- For all other platforms and configurations, the value returns `false`.

If the value is false and you try to open a window, SwiftUI ignores the action and logs a runtime error.

## Opening windows

- **Presenting windows and spaces**: Open and close the scenes that make up your app’s interface.
- **openWindow**: A window presentation action stored in a view’s environment.
- **OpenWindowAction**: An action that presents a window.
- **PushWindowAction**: An action that opens the requested window in place of the window the action is called from.

