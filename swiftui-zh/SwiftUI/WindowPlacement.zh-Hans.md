--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowPlacement
抓取时间：2025-12-02T17:21:21Z

---

# WindowPlacement

**Structure**

一种表示窗口首选大小和位置的类型。

## 声明

```swift
struct WindowPlacement
```

## 概述

使用 `Scene.defaultWindowPlacement(_:)` 修饰符时，您需要在提供的闭包中返回 `WindowPlacement` 的实例。

构造窗口位置时，许多初始参数是可选的。任何未指定的值都将回退到场景的默认行为和配置，用于调整窗口的大小和位置。

例如，您可以使用以下代码将窗口定位在屏幕可见区域底部上方 140 个点的位置：

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

## 结构体

- **WindowPlacement.Position**：窗口位置的语义值或位置值。

## 初始化器

- **init(_:)**：创建一个新的窗口位置，可选择指定位置。

- **init(_:size3D:)**：创建一个新的窗口位置，可选择指定位置和 3D 尺寸。对于不支持深度的场景，深度信息将被忽略。

- **init(_:size:)**：创建一个新的窗口位置，指定绝对位置和可选尺寸。

- **init(_:width:height:)**：创建一个新的窗口位置，指定显示相对位置，可选择指定宽度和高度。

- **init(_:width:height:depth:)**：创建一个新的窗口位置，可指定位置和 3D 尺寸。在不支持深度的场景或平台上，深度信息将被忽略。

- **init(x:y:width:height:)**：创建一个新的窗口位置，可指定位置和尺寸。

## 定位窗口

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：设置窗口的层级。

- **windowLevel(_:)**：设置当前场景的窗口层级。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **defaultWindowPlacement(_:)**：定义一个用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时的位置。

- **WindowPlacementContext**：一种表示用于调整窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：一种提供有关显示硬件信息的类型。

## 符合以下规范

- Equatable


---
source: https://developer.apple.com/documentation/SwiftUI/WindowPlacement
crawled: 2025-12-02T17:21:21Z
---

# WindowPlacement

**Structure**

A type which represents a preferred size and position for a window.

## Declaration

```swift
struct WindowPlacement
```

## Overview

When using the `Scene.defaultWindowPlacement(_:)` modifier, you return an instance of a `WindowPlacement` in the closure you provide.

When constructing a window placement, many initial parameters are optional. Any value not specified will fall back to the scene’s default behavior and configuration for sizing and positioning it’s windows.

For example, you can use this to position a window 140 points from the bottom of the visible area of the screen:

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

## Structures

- **WindowPlacement.Position**: A semantic or positional value for the location of a window.

## Initializers

- **init(_:)**: Creates a new window placement with an optional position.
- **init(_:size3D:)**: Creates a new window placement with an optional position and 3D size. Depth is ignored on scenes that don’t support it.
- **init(_:size:)**: Creates a new window placement with an absolute position and optional size.
- **init(_:width:height:)**: Creates a new window placement with a display-relative position, with an optional width and height.
- **init(_:width:height:depth:)**: Creates a new window placement with an optional position and 3D size. Depth is ignored on scenes or platforms that don’t support it.
- **init(x:y:width:height:)**: Creates a new window placement with an optional position and size.

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

## Conforms To

- Equatable

