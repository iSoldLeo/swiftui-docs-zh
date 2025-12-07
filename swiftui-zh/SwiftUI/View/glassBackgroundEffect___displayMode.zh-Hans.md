--- 来源：https://developer.apple.com/documentation/SwiftUI/View/glassBackgroundEffect(_:displayMode:)

抓取时间：2025-12-02T17:23:48Z

---

# glassBackgroundEffect(_:displayMode:)

**实例方法**

使用自定义玻璃背景效果和相对于容器的圆角矩形填充视图的背景。

## 声明

```swift
nonisolated func glassBackgroundEffect<S>(_ effect: S, displayMode: GlassBackgroundDisplayMode = .always) -> some View where S : GlassBackgroundEffect

```

## 参数

- **effect**：SwiftUI 用于绘制修改后视图背景的 [GlassBackgroundEffect](../GlassBackgroundEffect.zh-Hans.md) 实例。

- **displayMode**：何时显示玻璃背景。默认值为 [always](../GlassBackgroundDisplayMode/always.zh-Hans.md)。

## 返回值

带有玻璃背景的视图。

## 讨论

使用此修改器可添加玻璃材质，该材质可包含厚度、镜面反射、玻璃模糊、阴影和其他效果。由于其物理深度，背景会影响 Z 轴布局。为了获得不同的效果，背景可能会影响 X 轴和 Y 轴布局。

为确保将其添加到 [ZStack](../ZStack.zh-Hans.md) 中的视图集合时效果能够正确渲染，请将修改器添加到堆栈，而不是添加到堆栈中的某个视图。这包括使用视图修改器（例如 [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md) 或 [background(alignment:content:)](background_alignment_content.zh-Hans.md)）创建隐式堆栈的情况。在这些情况下，您可能需要在 `content` 闭包内创建一个显式的 [ZStack](../ZStack.zh-Hans.md)，以便添加背景修改器。

非封闭形状将渲染为其凸包。


---
source: https://developer.apple.com/documentation/SwiftUI/View/glassBackgroundEffect(_:displayMode:)
crawled: 2025-12-02T17:23:48Z
---

# glassBackgroundEffect(_:displayMode:)

**Instance Method**

Fills the view’s background with a custom glass background effect and container-relative rounded rectangle shape.

## Declaration

```swift
nonisolated func glassBackgroundEffect<S>(_ effect: S, displayMode: GlassBackgroundDisplayMode = .always) -> some View where S : GlassBackgroundEffect

```

## Parameters

- **effect**: A [GlassBackgroundEffect](../GlassBackgroundEffect.zh-Hans.md) instance that SwiftUI uses to draw a background of the modified view.
- **displayMode**: When to display the glass background. The default is [always](../GlassBackgroundDisplayMode/always.zh-Hans.md).

## Return Value

A view with a glass background.

## Discussion

Use this modifier to add a glass material that may include thickness, specularity, glass blur, shadows, and other effects. Because of its physical depth, the background influences z-axis layout. For different effect, the bakcground may influences x-axis and y-axis layout.

To ensure that the effect renders properly when you add it to a collection of views in a [ZStack](../ZStack.zh-Hans.md), add the modifier to the stack rather to one of the views in the stack. This includes when you create an implicit stack with view modifiers like [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md) or [background(alignment:content:)](background_alignment_content.zh-Hans.md). In those cases, you might need to create an explicit [ZStack](../ZStack.zh-Hans.md) inside the `content` closure to have a place to add the background modifier.

Non closed shapes will be rendered as their convex hull.

