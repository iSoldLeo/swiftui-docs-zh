--- 来源：https://developer.apple.com/documentation/SwiftUI/View/glassBackgroundEffect(in:displayMode:)

抓取时间：2025-11-30T21:18:48Z

---

# glassBackgroundEffect(in:displayMode:)

**实例方法**

使用您指定的形状和自动生成的玻璃背景效果填充视图的背景。

## 声明

```swift
nonisolated func glassBackgroundEffect<S>(in shape: S, displayMode: GlassBackgroundDisplayMode = .always) -> some View where S : InsettableShape

```

## 参数

- **shape**：SwiftUI 在视图后绘制的 [InsettableShape](../InsettableShape.zh-Hans.md) 实例。

- **displayMode**：何时显示玻璃背景。默认值为 [always](../GlassBackgroundDisplayMode/always.zh-Hans.md)。

## 返回值

带有玻璃背景的视图。

## 讨论

使用此修改器可添加包含厚度、镜面反射、玻璃模糊、阴影和其他效果的 3D 玻璃背景材质。由于其物理深度，玻璃背景会影响 Z 轴布局。

为确保将其添加到 [ZStack](../ZStack.zh-Hans.md) 中的视图集合时效果能够正确渲染，请将修改器添加到堆栈，而不是添加到堆栈中的某个视图。这包括使用视图修改器（例如 [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md) 或 [background(alignment:content:)](background_alignment_content.zh-Hans.md)）创建隐式堆栈的情况。在这些情况下，您可能需要在 `content` 闭包内创建一个显式的 [ZStack](../ZStack.zh-Hans.md)，以便添加玻璃背景修改器。

非封闭形状将渲染为其凸包。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：为视图背景自动填充玻璃背景效果，并设置相对于容器的圆角矩形形状。

- **GlassBackgroundDisplayMode**：玻璃背景的显示模式。

- **GlassBackgroundEffect**：玻璃背景外观的规范。

- **AutomaticGlassBackgroundEffect**：自动玻璃背景效果。

- **GlassBackgroundEffectConfiguration**：用于构建自定义效果的配置。

- **FeatheredGlassBackgroundEffect**：羽化玻璃背景效果。

- **PlateGlassBackgroundEffect**：平板玻璃背景效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/glassBackgroundEffect(in:displayMode:)
crawled: 2025-11-30T21:18:48Z
---

# glassBackgroundEffect(in:displayMode:)

**Instance Method**

Fills the view’s background with an automatic glass background effect and a shape that you specify.

## Declaration

```swift
nonisolated func glassBackgroundEffect<S>(in shape: S, displayMode: GlassBackgroundDisplayMode = .always) -> some View where S : InsettableShape

```

## Parameters

- **shape**: An [InsettableShape](../InsettableShape.zh-Hans.md) instance that SwiftUI draws behind the view.
- **displayMode**: When to display the glass background. The default is [always](../GlassBackgroundDisplayMode/always.zh-Hans.md).

## Return Value

A view with a glass background.

## Discussion

Use this modifier to add a 3D glass background material that includes thickness, specularity, glass blur, shadows, and other effects. Because of its physical depth, the glass background influences z-axis layout.

To ensure that the effect renders properly when you add it to a collection of views in a [ZStack](../ZStack.zh-Hans.md), add the modifier to the stack rather to one of the views in the stack. This includes when you create an implicit stack with view modifiers like [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md) or [background(alignment:content:)](background_alignment_content.zh-Hans.md). In those cases, you might need to create an explicit [ZStack](../ZStack.zh-Hans.md) inside the `content` closure to have a place to add the glass background modifier.

Non closed shapes will be rendered as their convex hull.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **GlassBackgroundDisplayMode**: The display mode of a glass background.
- **GlassBackgroundEffect**: A specification for the appearance of a glass background.
- **AutomaticGlassBackgroundEffect**: The automatic glass background effect.
- **GlassBackgroundEffectConfiguration**: A configuration used to build a custom effect.
- **FeatheredGlassBackgroundEffect**: The feathered glass background effect.
- **PlateGlassBackgroundEffect**: The plate glass background effect.

