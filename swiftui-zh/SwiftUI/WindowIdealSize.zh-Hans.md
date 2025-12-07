--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowIdealSize
抓取时间：2025-12-02T17:21:17Z

---

# WindowIdealSize

**Structure**

定义窗口缩放时应使用的尺寸类型。

## 声明

```swift
struct WindowIdealSize
```

## 概述

将此类型与 `Scene.windowIdealSize(_:)` 修饰符结合使用，可以覆盖窗口缩放时的默认行为。

例如，您可以定义一个窗口组，其中窗口的理想宽度为 800 点，理想高度为 600 点：

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(idealWidth: 800, idealHeight: 600)
        }
        .windowIdealSize(.fitToContent)
    }
}
```

## 类型属性

- **automatic**：自动窗口理想尺寸。 Windows 会根据系统行为来确定缩放时使用的尺寸。

- **fitToContent**：窗口理想尺寸，使用窗口内容的理想尺寸。

- **maximum**：窗口理想尺寸，使用窗口内容的最大尺寸。

## 调整窗口大小

- **定位和调整窗口大小**：影响应用程序显示的窗口的初始几何形状。

- **defaultSize(_:)**：设置窗口的默认大小。

- **defaultSize(width:height:)**：设置窗口的默认宽度和高度。

- **defaultSize(width:height:depth:)**：设置体感窗口的默认大小。

- **defaultSize(_:in:)**：设置体感窗口的默认大小。

- **defaultSize(width:height:depth:in:)**：设置体积窗口的默认大小。

- **windowResizability(_:)**：设置窗口的可调整大小方式。

- **WindowResizability**：窗口的可调整大小。

- **windowIdealSize(_:)**：指定从此场景派生的窗口在缩放时如何确定其大小。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/WindowIdealSize
crawled: 2025-12-02T17:21:17Z
---

# WindowIdealSize

**Structure**

A type which defines the size a window should use when zooming.

## Declaration

```swift
struct WindowIdealSize
```

## Overview

Use this type in conjunction with the `Scene.windowIdealSize(_:)` modifier to override the default behavior for how windows behave when performing a zoom.

For example, you can define a window group where the window has an ideal width of 800 points and an ideal height of 600 points:

```swift
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(idealWidth: 800, idealHeight: 600)
        }
        .windowIdealSize(.fitToContent)
    }
}
```

## Type Properties

- **automatic**: The automatic window ideal size. Windows will use the system behavior when determining the size to use when zooming.
- **fitToContent**: A window ideal size which uses the ideal size of the window’s contents.
- **maximum**: A window ideal size which uses the maximum size of the window’s contents.

## Sizing a window

- **Positioning and sizing windows**: Influence the initial geometry of windows that your app presents.
- **defaultSize(_:)**: Sets a default size for a window.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(_:in:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **windowResizability(_:)**: Sets the kind of resizability to use for a window.
- **WindowResizability**: The resizability of a window.
- **windowIdealSize(_:)**: Specifies how windows derived form this scene should determine their size when zooming.

## Conforms To

- Sendable
- SendableMetatype

