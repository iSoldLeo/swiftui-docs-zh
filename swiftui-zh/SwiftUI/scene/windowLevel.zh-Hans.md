--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowLevel(_:)

抓取时间：2025-12-02T17:21:20Z

---

# windowLevel(_:)

**实例方法**

设置此场景的窗口级别。

## 声明

```swift
nonisolated func windowLevel(_ level: WindowLevel) -> some Scene

```

## 参数

- **level**：期望的窗口级别

## 说明

```swift
Window("Utility Window", id: "...") {
    UtilityContent()
}
.windowLevel(.floating)
```

## 定位窗口

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：窗口的级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时使用的位置。

- **WindowPlacementContext**：表示用于调整窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：提供有关显示硬件的信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowLevel(_:)
crawled: 2025-12-02T17:21:20Z
---

# windowLevel(_:)

**Instance Method**

Sets the window level of this scene.

## Declaration

```swift
nonisolated func windowLevel(_ level: WindowLevel) -> some Scene

```

## Parameters

- **level**: The desired window level

## Discussion

```swift
Window("Utility Window", id: "...") {
    UtilityContent()
}
.windowLevel(.floating)
```

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

