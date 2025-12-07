--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/defaultWindowPlacement(_:)

抓取时间：2025-12-02T17:21:22Z

---

# defaultWindowPlacement(_:)

**实例方法**

定义一个用于确定窗口默认位置的函数。

## 声明

```swift
nonisolated func defaultWindowPlacement(_ makePlacement: @escaping (WindowLayoutRoot, WindowPlacementContext) -> WindowPlacement) -> some Scene

```

## 参数

- **makePlacement**：用于生成默认窗口位置的闭包。

## 说明

使用此场景修改器可以指定系统根据 [Scene](../Scene.zh-Hans.md) 声明创建的新窗口的默认初始大小和位置。

在 macOS 上，您可以使用屏幕边界来放置窗口。例如，您可以指定窗口始终位于屏幕底部上方 140 个点的位置：

```swift
struct MyApp: App {
    var body: some Scene {
        ...

        Window("Status", id: "status") {
            StatusView()
        }
        .windowResizability(.contentSize)
        .defaultWindowPlacement { content, context in
            let displayBounds = context.defaultDisplay.visibleRect
            let size = content.sizeThatFits(.unspecified)
            let position = CGPoint(
                x: displayBounds.midX - (size.width / 2),
                y: displayBounds.maxY - size.height - 140)
            return WindowPlacement(position: position, size: size)
        }
    }
}
```

在 visionOS 系统中，系统始终根据用户的视线位置放置第一个窗口。系统会忽略对 `defaultWindowPlacement(_:)` 的调用。

您可以通过返回 [Position](../WindowPlacement/Position.zh-Hans.md) 定义的方法之一并传入现有窗口，来将后续窗口相对于现有窗口放置。例如，您可以将新窗口与 `Content` 窗口的后缘对齐：

```swift
struct MyApp: App {
    @Environment(\.openWindow) private var openWindow

    var body: some Scene {
        WindowGroup("Content", id: "content") {
            Button("Open status window") {
                openWindow(id: "status")
            }
        }

        WindowGroup("Status", id: "status") {
            StatusView()
        }
        .windowResizability(.contentSize)
        .defaultWindowPlacement { content, context in
            if let contentWindow = context.windows.first(
            where: { $0.id == "content" }) {
                WindowPlacement(.trailing(contentWindow))
            } else {
                WindowPlacement()
            }
        }
    }
}
```

您的函数返回的位置将作为窗口首次出现时的默认位置。用户之后可以使用系统提供的界面控件调整窗口大小和位置。此外，在状态恢复期间，系统会将窗口恢复到其最近一次的大小和位置，而不是默认位置。

有关配置场景在状态恢复时的行为的更多信息，请参阅 `Scene.stateRestoration(_:)`。

## 定位窗口

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：窗口的级别。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时要使用的位置。

- **WindowPlacementContext**：表示用于调整窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：提供有关显示硬件信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/defaultWindowPlacement(_:)
crawled: 2025-12-02T17:21:22Z
---

# defaultWindowPlacement(_:)

**Instance Method**

Defines a function used for determining the default placement of windows.

## Declaration

```swift
nonisolated func defaultWindowPlacement(_ makePlacement: @escaping (WindowLayoutRoot, WindowPlacementContext) -> WindowPlacement) -> some Scene

```

## Parameters

- **makePlacement**: A closure to generate the default window placement.

## Discussion

Use this scene modifier to indicate a default initial size and position for a new window that the system creates from a [Scene](../Scene.zh-Hans.md) declaration.

On macOS, you can use the screen’s bounds to place the window. For example, you can specify that the window is always placed 140 points from the bottom of the screen:

```swift
struct MyApp: App {
    var body: some Scene {
        ...

        Window("Status", id: "status") {
            StatusView()
        }
        .windowResizability(.contentSize)
        .defaultWindowPlacement { content, context in
            let displayBounds = context.defaultDisplay.visibleRect
            let size = content.sizeThatFits(.unspecified)
            let position = CGPoint(
                x: displayBounds.midX - (size.width / 2),
                y: displayBounds.maxY - size.height - 140)
            return WindowPlacement(position: position, size: size)
        }
    }
}
```

On visionOS, the system always places the first window relative to where the person is looking. The system ignores calls to `defaultWindowPlacement(_:)`.

You can place any subsequent windows relative to existing ones by returning one of the methods defined by [Position](../WindowPlacement/Position.zh-Hans.md) with the existing window. For example, you can align the new window with the trailing edge of the `Content` window:

```swift
struct MyApp: App {
    @Environment(\.openWindow) private var openWindow

    var body: some Scene {
        WindowGroup("Content", id: "content") {
            Button("Open status window") {
                openWindow(id: "status")
            }
        }

        WindowGroup("Status", id: "status") {
            StatusView()
        }
        .windowResizability(.contentSize)
        .defaultWindowPlacement { content, context in
            if let contentWindow = context.windows.first(
            where: { $0.id == "content" }) {
                WindowPlacement(.trailing(contentWindow))
            } else {
                WindowPlacement()
            }
        }
    }
}
```

The placement that your function returns acts as a default for when the window first appears. People can later resize and move the window using interface controls that the system provides. Also, during state restoration, the system restores the window to it’s most recent size and position, rather than the default placement.

For more information on configuring how scenes behave with state restoration, see `Scene.stateRestoration(_:)`.

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

