--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowProxy
抓取时间：2025-12-02T17:21:24Z

---

# WindowProxy

**Structure**

应用程序中已打开窗口的代理。

## 声明

```swift
struct WindowProxy
```

## 实例属性

- **id**：窗口的 ID（如果已提供）。

- **phase**：窗口的当前 [ScenePhase](ScenePhase.zh-Hans.md)。

## 窗口定位

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：窗口的级别。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时使用的位置。

- **WindowPlacementContext**：表示用于调整窗口大小和位置的上下文信息的类型。

- **DisplayProxy**：提供有关显示硬件的信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowProxy
crawled: 2025-12-02T17:21:24Z
---

# WindowProxy

**Structure**

The proxy for an open window in the app.

## Declaration

```swift
struct WindowProxy
```

## Instance Properties

- **id**: The ID for the window, if one was provided.
- **phase**: The window’s current [ScenePhase](ScenePhase.zh-Hans.md).

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **DisplayProxy**: A type which provides information about display hardware.

