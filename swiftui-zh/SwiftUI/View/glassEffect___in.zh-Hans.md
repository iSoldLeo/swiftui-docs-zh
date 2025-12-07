--- 来源：https://developer.apple.com/documentation/SwiftUI/View/glassEffect(_:in:)

抓取时间：2025-11-30T21:08:53Z

---

# glassEffect(_:in:)

**实例方法**

将 Liquid Glass 效果应用于视图。

## 声明

```swift
nonisolated func glassEffect(_ glass: Glass = .regular, in shape: some Shape = DefaultGlassEffectShape()) -> some View

```

## 说明

使用此效果时，系统会：

- 渲染一个锚定在视图后面的形状，并使用 Liquid Glass 材质。

- 将 Liquid Glass 的前景效果应用于视图。

例如，要将此效果添加到 [Text](../Text.zh-Hans.md)：

```swift
Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect()
```

SwiftUI 默认使用 [regular](../Glass/regular.zh-Hans.md) 变体以及 [Capsule](../Capsule.zh-Hans.md) 形状。 SwiftUI 将 Liquid Glass 锚定到视图的边界。在上面的示例中，材质填充了整个 `Text` 框架，包括内边距。

通常，您会将此修饰符与 [GlassEffectContainer](../GlassEffectContainer.zh-Hans.md) 一起使用，以将多个 Liquid Glass 形状合并为一个可以相互变形的单一形状。

## 使用 Liquid Glass 设置视图样式

- **将 Liquid Glass 应用于自定义视图**：使用 Liquid Glass 效果配置、合并和变形视图。

- **里程碑：使用 Liquid Glass 构建应用**：使用系统提供的和自定义的 Liquid Glass 增强您的应用体验。

- **interactive(_:)**：返回配置为交互式的结构副本。

- **GlassEffectContainer**：将多个 Liquid Glass 形状合并为一个可以相互变形的单一形状的视图。

- **GlassEffectTransition**：用于描述在视图层级结构中添加或移除玻璃效果时要应用的更改的结构。

- **GlassButtonStyle**：一种按钮样式，可根据按钮的上下文应用玻璃边框图案。

- **GlassProminentButtonStyle**：一种按钮样式，可根据按钮的上下文应用醒目的玻璃边框图案。

- **DefaultGlassEffectShape**：玻璃效果应用的默认形状，即胶囊体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/glassEffect(_:in:)
crawled: 2025-11-30T21:08:53Z
---

# glassEffect(_:in:)

**Instance Method**

Applies the Liquid Glass effect to a view.

## Declaration

```swift
nonisolated func glassEffect(_ glass: Glass = .regular, in shape: some Shape = DefaultGlassEffectShape()) -> some View

```

## Discussion

When you use this effect, the system:

- Renders a shape anchored behind a view with the Liquid Glass material.
- Applies the foreground effects of Liquid Glass over a view.

For example, to add this effect to a [Text](../Text.zh-Hans.md):

```swift
Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect()
```

SwiftUI uses the [regular](../Glass/regular.zh-Hans.md) variant by default along with a [Capsule](../Capsule.zh-Hans.md) shape.

SwiftUI anchors the Liquid Glass to a view’s bounds. For the example above, the material fills the entirety of the `Text` frame, which includes the padding.

You typically use this modifier with a [GlassEffectContainer](../GlassEffectContainer.zh-Hans.md) to combine multiple Liquid Glass shapes into a single shape that can morph into one another.

## Styling views with Liquid Glass

- **Applying Liquid Glass to custom views**: Configure, combine, and morph views using Liquid Glass effects.
- **Landmarks: Building an app with Liquid Glass**: Enhance your app experience with system-provided and custom Liquid Glass.
- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **GlassEffectContainer**: A view that combines multiple Liquid Glass shapes into a single shape that can morph individual shapes into one another.
- **GlassEffectTransition**: A structure that describes changes to apply when a glass effect is added or removed from the view hierarchy.
- **GlassButtonStyle**: A button style that applies glass border artwork based on the button’s context.
- **GlassProminentButtonStyle**: A button style that applies prominent glass border artwork based on the button’s context.
- **DefaultGlassEffectShape**: The default shape applied by glass effects, a capsule.

