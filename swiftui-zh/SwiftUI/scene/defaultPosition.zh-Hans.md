--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/defaultPosition(_:)

抓取时间：2025-12-02T17:21:18Z

---

# defaultPosition(_:)

**实例方法**

设置窗口的默认位置。

## 声明

```swift
nonisolated func defaultPosition(_ position: UnitPoint) -> some Scene

```

## 参数

- **position**：一个 [UnitPoint](../UnitPoint.zh-Hans.md)，用于指定新打开的窗口相对于屏幕边界的位置。

## 返回值

一个使用默认位置放置新窗口的场景。

## 说明

首次从特定场景声明打开窗口时，系统默认会将窗口放置在屏幕中心。对于支持多个同时显示的场景类型，系统会将每个新增窗口略微偏移，以避免完全遮挡现有窗口。

您可以通过应用场景修改器来覆盖第一个窗口的默认位置，该修改器指示窗口相对于屏幕边界的放置位置。例如，您可以请求系统将新窗口放置在屏幕的底部后角：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .defaultPosition(.bottomTrailing)
    }
}
```

系统会将窗口中与指定的 [UnitPoint](../UnitPoint.zh-Hans.md) 对应的点与屏幕上与同一单位点对应的点对齐。

您通常使用预定义的单位点之一（例如上例中的 [bottomTrailing](../UnitPoint/bottomTrailing.zh-Hans.md)），但您也可以使用自定义单位点。例如，以下修改器将窗口前缘四分之一处的点与屏幕前缘四分之一处的点对齐，同时使窗口在 y 轴上居中：

```swift
WindowGroup {
    ContentView()
}
.defaultPosition(UnitPoint(x: 0.25, y: 0.5))
```

此修改器会影响 macOS 中所有创建窗口的场景类型，包括：

- [WindowGroup](../WindowGroup.zh-Hans.md)

- [Window](../Window.zh-Hans.md)

- [DocumentGroup](../DocumentGroup.zh-Hans.md)

- [Settings](../Settings.zh-Hans.md)

您提供的值仅作为初始默认值。在状态恢复期间，系统会将窗口恢复到其最后所在的位置。

## 定位窗口

- **WindowLevel**：窗口的级别。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时使用的位置。

- **WindowPlacementContext**：表示用于调整窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：提供有关显示硬件的信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/defaultPosition(_:)
crawled: 2025-12-02T17:21:18Z
---

# defaultPosition(_:)

**Instance Method**

Sets a default position for a window.

## Declaration

```swift
nonisolated func defaultPosition(_ position: UnitPoint) -> some Scene

```

## Parameters

- **position**: A [UnitPoint](../UnitPoint.zh-Hans.md) that specifies where to place a newly opened window relative to the screen bounds.

## Return Value

A scene that uses a default position for new windows.

## Discussion

The first time your app opens a window from a particular scene declaration, the system places the window at the center of the screen by default. For scene types that support multiple simultaneous windows, the system offsets each additional window by a small amount to avoid completely obscuring existing windows.

You can override the default placement of the first window by applying a scene modifier that indicates where to place the window relative to the screen bounds. For example, you can request that the system place a new window in the bottom trailing corner of the screen:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .defaultPosition(.bottomTrailing)
    }
}
```

The system aligns the point in the window that corresponds to the specified [UnitPoint](../UnitPoint.zh-Hans.md) with the point in the screen that corresponds to the same unit point.

You typically use one of the predefined unit points — like [bottomTrailing](../UnitPoint/bottomTrailing.zh-Hans.md) in the above example — but you can also use a custom unit point. For example, the following modifier aligns the point that’s one quarter of the way from the leading edge of the window with the point that’s one quarter of the way from the leading edge of the screen, while centering the window in the y-dimension:

```swift
WindowGroup {
    ContentView()
}
.defaultPosition(UnitPoint(x: 0.25, y: 0.5))
```

The modifier affects any scene type that creates windows in macOS, namely:

- [WindowGroup](../WindowGroup.zh-Hans.md)
- [Window](../Window.zh-Hans.md)
- [DocumentGroup](../DocumentGroup.zh-Hans.md)
- [Settings](../Settings.zh-Hans.md)

The value that you provide acts only as an initial default. During state restoration, the system restores the window to the position that it last occupied.

## Positioning a window

- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

