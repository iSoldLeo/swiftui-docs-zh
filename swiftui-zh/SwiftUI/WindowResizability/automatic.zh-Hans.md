---
来源： https://developer.apple.com/documentation/SwiftUI/WindowResizability/automatic
抓取时间： 2025-12-03T05:32:04Z
---

# 自动

**类型属性**

自动调整窗口大小。

## 声明

```swift
static var automatic: WindowResizability { get set }
```

## 讨论

使用自动调整大小功能时，SwiftUI 会应用适合场景类型的调整大小策略：

- 来自[WindowGroup](../WindowGroup.zh-Hans.md)、[Window](../Window.zh-Hans.md) 和[DocumentGroup](../DocumentGroup.zh-Hans.md) 场景声明的窗口使用[contentMinSize](contentMinSize.zh-Hans.md) 策略。
- 来自[Settings](../Settings.zh-Hans.md)场景声明的窗口使用[contentSize](contentSize.zh-Hans.md)策略。
- 在 visionOS 上，窗口样式为 [volumetric](../WindowStyle/volumetric.zh-Hans.md) 的窗口使用 [contentSize](contentSize.zh-Hans.md) 策略。

如果不使用 [windowResizability(_:)](../scene/windowResizability.zh-Hans.md) 场景修改器指定其他值，默认情况下会自动调整大小。

## 获取可调整大小

- **contentMinSize**：窗口的可调整性，部分来源于窗口内容。
- **contentSize**：从窗口内容导出的窗口大小可调整性。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowResizability/automatic
crawled: 2025-12-03T05:32:04Z
---

# automatic

**Type Property**

The automatic window resizability.

## Declaration

```swift
static var automatic: WindowResizability { get set }
```

## Discussion

When you use automatic resizability, SwiftUI applies a resizing strategy that’s appropriate for the scene type:

- Windows from [WindowGroup](../WindowGroup.zh-Hans.md), [Window](../Window.zh-Hans.md), and [DocumentGroup](../DocumentGroup.zh-Hans.md) scene declarations use the [contentMinSize](contentMinSize.zh-Hans.md) strategy.
- A window from a [Settings](../Settings.zh-Hans.md) scene declaration uses the [contentSize](contentSize.zh-Hans.md) strategy.
- Windows on visionOS with a window style of [volumetric](../WindowStyle/volumetric.zh-Hans.md) use the [contentSize](contentSize.zh-Hans.md) strategy.

Automatic resizability is the default if you don’t specify another value using the [windowResizability(_:)](../scene/windowResizability.zh-Hans.md) scene modifier.

## Getting the resizability

- **contentMinSize**: A window resizability that’s partially derived from the window’s content.
- **contentSize**: A window resizability that’s derived from the window’s content.

