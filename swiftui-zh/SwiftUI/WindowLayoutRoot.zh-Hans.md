---
来源： https://developer.apple.com/documentation/SwiftUI/WindowLayoutRoot
抓取时间： 2025-12-02T17:21:20Z
---

# WindowLayoutRoot

**Structure**

表示窗口根内容的代理。

## 声明

```swift
struct WindowLayoutRoot
```

## 概览

该类型类似于 SwiftUI [Scene](Scene.zh-Hans.md) 所定义窗口内容的代理。`Scene.defaultWindowPlacement(_:)`修饰符接收此类型的实例，代表正在创建的窗口的内容。

使用该代理可获取窗口内容的相关信息，如窗口大小。

### 实例方法

- **sizeThatFits(_:)**：询问窗口内容的大小。

## 定位窗口

- **defaultPosition(_:)**：设置窗口的默认位置。
- **WindowLevel**：窗口的级别。
- **windowLevel(_:)**：设置此场景的窗口级别。
- **WindowPlacement**：表示窗口首选大小和位置的类型。
- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。
- **windowIdealPlacement(_:)**：定义用于确定窗口默认位置的函数：提供一个函数，用于确定场景窗口缩放时的位置。
- **WindowPlacementContext**：一种表示上下文信息的类型，用于调整窗口大小和位置。
- **WindowProxy**：应用程序中打开窗口的代理。
- **DisplayProxy**：提供显示硬件信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowLayoutRoot
crawled: 2025-12-02T17:21:20Z
---

# WindowLayoutRoot

**Structure**

A proxy which represents the root contents of a window.

## Declaration

```swift
struct WindowLayoutRoot
```

## Overview

This type acts like a proxy for the contents of the window defined by a SwiftUI [Scene](Scene.zh-Hans.md). The `Scene.defaultWindowPlacement(_:)` modifier receives an instance of this type, representing the contents of the window being created.

Use this proxy to get information about the window’s contents, like it’s size.

## Instance Methods

- **sizeThatFits(_:)**: Asks the window’s content for its size.

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

