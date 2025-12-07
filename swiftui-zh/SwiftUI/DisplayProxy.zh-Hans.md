--- 来源：https://developer.apple.com/documentation/SwiftUI/DisplayProxy
抓取时间：2025-12-02T17:21:25Z

---

# DisplayProxy

**Structure**

一种提供显示硬件信息的类型。

## 声明

```swift
struct DisplayProxy
```

## 概述

您可以将此类型与自定义窗口布局一起使用，以根据显示器的边界调整窗口的大小和位置。

例如，您的自定义窗口布局可以将窗口定位在距离屏幕可见区域底部 140 个点的位置：

```swift
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
```

## 实例属性

- **bounds**：显示器的完整尺寸，包括系统界面元素占用的空间。

- **safeAreaInsets**：此显示器的安全区域内边距。

- **visibleRect**：显示器上可以安全放置窗口的区域。

## 定位窗口

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：窗口的级别。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时的位置。

- **WindowPlacementContext**：一种表示用于调整窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

## 符合以下标准

- Equatable


---
source: https://developer.apple.com/documentation/SwiftUI/DisplayProxy
crawled: 2025-12-02T17:21:25Z
---

# DisplayProxy

**Structure**

A type which provides information about display hardware.

## Declaration

```swift
struct DisplayProxy
```

## Overview

You can use this type with your custom window layouts to size and position windows relative to a display’s bounds.

For example, your custom window layout can position a window 140 points from the bottom of the screen’s visible area:

```swift
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
```

## Instance Properties

- **bounds**: The full dimensions of the display, including any space occupied by system interface elements.
- **safeAreaInsets**: The safe area inset of this display.
- **visibleRect**: The portion of the display where it is safe to place windows.

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.

## Conforms To

- Equatable

