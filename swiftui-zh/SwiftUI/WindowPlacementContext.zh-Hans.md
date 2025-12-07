--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowPlacementContext
抓取时间：2025-12-02T17:21:23Z

---

# WindowPlacementContext

**Structure**

一种用于表示窗口大小和位置的上下文信息的类型。

## 声明

```swift
struct WindowPlacementContext
```

## 概述

放置上下文提供的信息用于通过提供给 `defaultWindowPlacement(_:)` 修饰符的闭包来提供新的放置位置。

## 实例属性

- **defaultDisplay**：默认情况下，新窗口将显示在哪个显示器上。

- **windows**：当前活动场景列表

## 窗口定位

- **defaultPosition(_:)**：设置窗口的默认位置。

- **WindowLevel**：窗口的级别。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时使用的位置。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：提供有关显示硬件信息的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowPlacementContext
crawled: 2025-12-02T17:21:23Z
---

# WindowPlacementContext

**Structure**

A type which represents contextual information used for sizing and positioning windows.

## Declaration

```swift
struct WindowPlacementContext
```

## Overview

The placement context provides information to be used when providing a new placement via the closure provided to the `defaultWindowPlacement(_:)` modifier.

## Instance Properties

- **defaultDisplay**: The display on which new windows will be presented by default.
- **windows**: The list of current active scenes

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **WindowLevel**: The level of a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

