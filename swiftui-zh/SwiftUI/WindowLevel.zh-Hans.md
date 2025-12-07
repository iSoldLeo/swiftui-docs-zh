--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowLevel
抓取时间：2025-12-02T17:21:19Z

---

# WindowLevel

**Structure**

窗口级别。

## 声明

```swift
struct WindowLevel
```

## 概述

与 `.windowLevel(_:)` 修饰符结合使用，可控制窗口级别。

## 类型属性

- **automatic**：自动窗口级别。

- **desktop**：桌面窗口级别。

- **floating**：浮动窗口级别。

- **normal**：普通窗口级别。

## 窗口定位

- **defaultPosition(_:)**：设置窗口的默认位置。

- **windowLevel(_:)**：设置此场景的窗口级别。

- **WindowLayoutRoot**：表示窗口根内容的代理。

- **WindowPlacement**：表示窗口首选大小和位置的类型。

- **defaultWindowPlacement(_:)**：定义用于确定窗口默认位置的函数。

- **windowIdealPlacement(_:)**：提供一个函数，用于确定场景窗口缩放时使用的位置。

- **WindowPlacementContext**：表示用于调整窗口大小和位置的上下文信息的类型。

- **WindowProxy**：应用程序中已打开窗口的代理。

- **DisplayProxy**：一种提供显示硬件信息的类型。

## 符合以下规范

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/WindowLevel
crawled: 2025-12-02T17:21:19Z
---

# WindowLevel

**Structure**

The level of a window.

## Declaration

```swift
struct WindowLevel
```

## Overview

Use this in conjunction with the `.windowLevel(_:)` modifier to control window levels.

## Type Properties

- **automatic**: Automatic window level.
- **desktop**: Desktop window level.
- **floating**: Floating window level.
- **normal**: Normal window level.

## Positioning a window

- **defaultPosition(_:)**: Sets a default position for a window.
- **windowLevel(_:)**: Sets the window level of this scene.
- **WindowLayoutRoot**: A proxy which represents the root contents of a window.
- **WindowPlacement**: A type which represents a preferred size and position for a window.
- **defaultWindowPlacement(_:)**: Defines a function used for determining the default placement of windows.
- **windowIdealPlacement(_:)**: Provides a function which determines a placement to use when windows of a scene zoom.
- **WindowPlacementContext**: A type which represents contextual information used for sizing and positioning windows.
- **WindowProxy**: The proxy for an open window in the app.
- **DisplayProxy**: A type which provides information about display hardware.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

