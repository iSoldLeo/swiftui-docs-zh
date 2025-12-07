---
来源： https://developer.apple.com/documentation/SwiftUI/WindowResizability
抓取时间： 2025-12-02T17:21:15Z
---

# WindowResizability

**Structure**

窗口大小的可调整性。

## 声明

```swift
struct WindowResizability
```

## 概览

使用[windowResizability(_:)](scene/windowResizability.zh-Hans.md) 场景修改器将此类型的值应用到您在[Scene](Scene.zh-Hans.md) 声明中定义的[App](App.zh-Hans.md) 中。您指定的值表示系统对从该场景创建的窗口施加最小和最大尺寸限制时使用的策略。

例如，您可以创建一个窗口组，通过对场景内容应用具有这些限制的框架，以及对场景应用[contentSize](WindowResizability/contentSize.zh-Hans.md)可调整性，使人们可以将两个维度的大小调整到 100 到 400 点之间：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(
                    minWidth: 100, maxWidth: 400,
                    minHeight: 100, maxHeight: 400)
        }
        .windowResizability(.contentSize)
    }
}
```

如果不应用修改器，所有场景的默认值都是[automatic](WindowResizability/automatic.zh-Hans.md)。在该策略下，[Settings](Settings.zh-Hans.md) 窗口使用[contentSize](WindowResizability/contentSize.zh-Hans.md) 策略，而其他所有窗口则使用[contentMinSize](WindowResizability/contentMinSize.zh-Hans.md)。在 visionOS 上，窗口样式为 [volumetric](WindowStyle/volumetric.zh-Hans.md) 的窗口也使用[contentSize](WindowResizability/contentSize.zh-Hans.md) 策略。

## 获取可调整性

- **automatic**：自动调整窗口大小。
- **contentMinSize**：部分源自窗口内容的窗口可调整性。
- **contentSize**：从窗口内容导出的窗口大小可变性。

## 调整窗口大小

- 定位和调整窗口大小**：影响应用程序显示窗口的初始几何形状。
- **defaultSize(_:)**：设置窗口的默认大小。
- **defaultSize(width:height:)**: 设置窗口的默认宽度和高度：为窗口设置默认宽度和高度。
- **defaultSize(width:height:depth:)**：为窗口设置默认宽度和高度：设置容积窗口的默认大小。
- **defaultSize(_:in:)**：设置容积窗口的默认大小。
- **defaultSize(width:height:depth:in:)**：设置容积窗口的默认大小。
- **windowResizability(_:)**：为窗口设置可调整大小的类型。
- **windowIdealSize(_:)**：指定缩放时从该场景派生的窗口应如何确定其大小。
- **WindowIdealSize**：一种类型，用于定义缩放时窗口应使用的大小。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WindowResizability
crawled: 2025-12-02T17:21:15Z
---

# WindowResizability

**Structure**

The resizability of a window.

## Declaration

```swift
struct WindowResizability
```

## Overview

Use the [windowResizability(_:)](scene/windowResizability.zh-Hans.md) scene modifier to apply a value of this type to a [Scene](Scene.zh-Hans.md) that you define in your [App](App.zh-Hans.md) declaration. The value that you specify indicates the strategy the system uses to place minimum and maximum size restrictions on windows that it creates from that scene.

For example, you can create a window group that people can resize to between 100 and 400 points in both dimensions by applying both a frame with those constraints to the scene’s content, and the [contentSize](WindowResizability/contentSize.zh-Hans.md) resizability to the scene:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
                .frame(
                    minWidth: 100, maxWidth: 400,
                    minHeight: 100, maxHeight: 400)
        }
        .windowResizability(.contentSize)
    }
}
```

The default value for all scenes if you don’t apply the modifier is [automatic](WindowResizability/automatic.zh-Hans.md). With that strategy, [Settings](Settings.zh-Hans.md) windows use the [contentSize](WindowResizability/contentSize.zh-Hans.md) strategy, while all others use [contentMinSize](WindowResizability/contentMinSize.zh-Hans.md). Windows on visionOS with a window style of [volumetric](WindowStyle/volumetric.zh-Hans.md) also use the [contentSize](WindowResizability/contentSize.zh-Hans.md) strategy.

## Getting the resizability

- **automatic**: The automatic window resizability.
- **contentMinSize**: A window resizability that’s partially derived from the window’s content.
- **contentSize**: A window resizability that’s derived from the window’s content.

## Sizing a window

- **Positioning and sizing windows**: Influence the initial geometry of windows that your app presents.
- **defaultSize(_:)**: Sets a default size for a window.
- **defaultSize(width:height:)**: Sets a default width and height for a window.
- **defaultSize(width:height:depth:)**: Sets a default size for a volumetric window.
- **defaultSize(_:in:)**: Sets a default size for a volumetric window.
- **defaultSize(width:height:depth:in:)**: Sets a default size for a volumetric window.
- **windowResizability(_:)**: Sets the kind of resizability to use for a window.
- **windowIdealSize(_:)**: Specifies how windows derived form this scene should determine their size when zooming.
- **WindowIdealSize**: A type which defines the size a window should use when zooming.

## Conforms To

- Sendable
- SendableMetatype

