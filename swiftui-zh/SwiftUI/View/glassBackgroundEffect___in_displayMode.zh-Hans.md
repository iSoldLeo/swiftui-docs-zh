--- 来源：https://developer.apple.com/documentation/SwiftUI/View/glassBackgroundEffect(_:in:displayMode:)

抓取时间：2025-12-02T17:23:49Z

---

# glassBackgroundEffect(_:in:displayMode:)

**实例方法**

使用您指定的自定义玻璃背景效果和形状填充视图的背景。

## 声明

```swift
nonisolated func glassBackgroundEffect<T, S>(_ effect: S, in shape: T, displayMode: GlassBackgroundDisplayMode = .always) -> some View where T : InsettableShape, S : GlassBackgroundEffect

```

## 参数

- **effect**：SwiftUI 用于填充您指定的背景形状的 [GlassBackgroundEffect](../GlassBackgroundEffect.zh-Hans.md) 实例。

- **shape**：SwiftUI 在视图后面绘制的 [InsettableShape](../InsettableShape.zh-Hans.md) 实例。

- **displayMode**：何时显示玻璃背景。默认值为 [always](../GlassBackgroundDisplayMode/always.zh-Hans.md)。

## 返回值

一个带有玻璃背景的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/glassBackgroundEffect(_:in:displayMode:)
crawled: 2025-12-02T17:23:49Z
---

# glassBackgroundEffect(_:in:displayMode:)

**Instance Method**

Fills the view’s background with a custom glass background effect and a shape that you specify.

## Declaration

```swift
nonisolated func glassBackgroundEffect<T, S>(_ effect: S, in shape: T, displayMode: GlassBackgroundDisplayMode = .always) -> some View where T : InsettableShape, S : GlassBackgroundEffect

```

## Parameters

- **effect**: A [GlassBackgroundEffect](../GlassBackgroundEffect.zh-Hans.md) instance that SwiftUI uses to the fill the background shape that you specify.
- **shape**: An [InsettableShape](../InsettableShape.zh-Hans.md) instance that SwiftUI draws behind the view.
- **displayMode**: When to display the glass background. The default is [always](../GlassBackgroundDisplayMode/always.zh-Hans.md).

## Return Value

A view with a glass background.

