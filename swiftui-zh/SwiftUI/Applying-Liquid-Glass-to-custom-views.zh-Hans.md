--- 来源：https://developer.apple.com/documentation/SwiftUI/Applying-Liquid-Glass-to-custom-views

抓取时间：2025-12-02T17:02:03Z

---

# 将 Liquid Glass 应用于自定义视图

**Article**

使用 Liquid Glass 效果配置、组合和变形视图。

## 概述

Apple 各平台界面均采用一种名为 Liquid Glass 的全新动态材质，它将玻璃的光学特性与流动性完美结合。Liquid Glass 材质能够模糊其后的内容，反射周围内容的颜色和光线，并实时响应触摸和指针交互。SwiftUI 中的标准组件均使用 Liquid Glass。在自定义组件上应用 Liquid Glass，即可使用独特的动画和过渡效果移动、组合和变形组件。

要了解有关 Liquid Glass 的更多信息，请参阅 [Landmarks-Building-an-app-with-Liquid-Glass](Landmarks-Building-an-app-with-Liquid-Glass.zh-Hans.md)。

## 应用和配置液态玻璃效果

使用 [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) 修饰符为视图添加液态玻璃效果。默认情况下，该修饰符使用 [Glass](Glass.zh-Hans.md) 的变体 [regular](Glass/regular.zh-Hans.md)，并将给定效果应用于视图内容后面的 [Capsule](Capsule.zh-Hans.md) 形状内。

配置效果以多种方式自定义组件：

- 使用不同的形状，使应用程序中的自定义组件外观一致。例如，如果将效果应用于较大的组件，而使用 `Capsule` 或 [Circle](Circle.zh-Hans.md) 则效果不佳，则可以使用圆角矩形。

- 指定色调以突出显示效果。

- 将 [interactive(_:)](Glass/interactive.zh-Hans.md) 添加到自定义组件，使其能够响应触摸和指针交互。这会应用与 [glass](PrimitiveButtonStyle/glass.zh-Hans.md) 为标准按钮提供的相同的响应式和流畅式效果。

在以下示例中，观察如何将液态玻璃效果应用于视图、使用具有特定圆角半径的替代形状，以及创建响应交互的着色视图：

```swift
Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect()

Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect(in: .rect(cornerRadius: 16.0))

Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect(.regular.tint(.orange).interactive())
```

## 将多个视图与液态玻璃容器组合

在多个视图上应用液态玻璃效果时，请使用 [GlassEffectContainer](GlassEffectContainer.zh-Hans.md) 以获得最佳渲染性能。容器还允许具有液态玻璃效果的视图将其形状混合在一起，并在过渡期间相互变形。在容器内，每个带有 [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) 修改器的视图都会渲染其背后的效果。

自定义容器上的间距以控制视图背后的液态玻璃效果如何相互交互。容器上的间距值越大，视图背后的液态玻璃效果混合在一起并在过渡期间合并形状的速度就越快。容器上的间距值如果大于内部 [HStack](HStack.zh-Hans.md)、[VStack](VStack.zh-Hans.md) 或其他布局容器的间距，则静态时“液态玻璃”效果会融合在一起，因为视图彼此距离太近。当视图以动画形式出现或消失时，随着容器内空间的变化，形状会随之变形或融合。

`glassEffect(_:in:)` 修改器用于捕获要发送到容器进行渲染的内容。在其他影响视图外观的修改器之后应用 `glassEffect(_:in:)` 修改器。

在下面的示例中，两张图片彼此靠近，“液态玻璃”效果开始将它们的形状融合在一起。这会在组件在容器内相互移动时产生流畅的动画效果：

```swift
GlassEffectContainer(spacing: 40.0) {
    HStack(spacing: 40.0) {
        Image(systemName: "scribble.variable")
            .frame(width: 80.0, height: 80.0)
            .font(.system(size: 36))
            .glassEffect()

        Image(systemName: "eraser.fill")
            .frame(width: 80.0, height: 80.0)
            .font(.system(size: 36))
            .glassEffect()

            // An `offset` shows how Liquid Glass effects react to each other in a container.
            // Use animations and components appearing and disappearing to obtain effects that look purposeful.
            .offset(x: -40.0, y: 0.0)
    }
}
```

在某些情况下，即使内容处于静态状态，您也希望多个视图的几何体共同构成一个“液态玻璃”效果胶囊。使用 [glassEffectUnion(id:namespace:)](View/glassEffectUnion_id_namespace.zh-Hans.md) 修改器可以指定视图参与具有特定 ID 的统一效果。这会将所有形状相似、具有液态玻璃效果且 ID 相同的效果合并为一个应用了液态玻璃材质的单一形状。这在动态创建视图或创建位于布局容器（例如 `HStack` 或 `VStack`）之外的视图时尤其有用。

```swift
let symbolSet: [String] = ["cloud.bolt.rain.fill", "sun.rain.fill", "moon.stars.fill", "moon.fill"]

GlassEffectContainer(spacing: 20.0) {
    HStack(spacing: 20.0) {
        ForEach(symbolSet.indices, id: \.self) { item in
            Image(systemName: symbolSet[item])
                .frame(width: 80.0, height: 80.0)
                .font(.system(size: 36))
                .glassEffect()
                .glassEffectUnion(id: item < 2 ? "1" : "2", namespace: namespace)
        }
    }
}
```

## 在过渡期间变形液态玻璃效果

在具有液态玻璃效果的视图之间的过渡或动画期间，会发生变形效果。使用 [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md) 修改器可以协调容器中具有效果的视图之间的过渡。[GlassEffectTransition](GlassEffectTransition.zh-Hans.md) 允许您指定在容器内添加或移除效果时要使用的过渡类型。对于位于容器指定间距内的特效，默认过渡类型为 [matchedGeometry](GlassEffectTransition/matchedGeometry.zh-Hans.md)。

如果您希望使用更简单的过渡效果或创建自定义过渡效果，请使用 [materialize](GlassEffectTransition/materialize.zh-Hans.md) 和 [withAnimation(_:_:)](withAnimation.zh-Hans.md) 过渡效果。对于位于容器指定间距之外的特效，请使用 `materialize` 过渡效果。为了确保用户体验的一致性，请在所有应用中使用 `matchedGeometry` 和 `materialize` 过渡效果。系统提供的过渡类型不仅限于透明度变化。

将每个“液态玻璃”特效与 [Namespace](Namespace.zh-Hans.md) 属性包装器提供的命名空间中的唯一标识符关联起来。这些 ID 可确保当视图层级结构发生变化导致形状出现或消失时，SwiftUI 能够正确地为相同的形状添加动画效果。 SwiftUI 会利用效果容器的间距以及形状本身的几何形状来确定何时以及从哪个合适的形状变形或变出。

`glassEffectID(_:in:)` 和 `glassEffectTransition(_:)` 修饰符仅在视图层级转换或动画期间影响其内容。

在下面的示例中，当 `isExpanded` 变量发生变化时，橡皮擦图像会从铅笔图像过渡到橡皮擦图像，然后再从铅笔图像过渡出来。`GlassEffectContainer` 的间距值为 `40.0`，而其内部的 `HStack` 的间距值为 `40.0`。当橡皮擦的最近边缘小于或等于容器的间距时，橡皮擦图像会变形为铅笔图像。

```swift
@State private var isExpanded: Bool = false
@Namespace private var namespace

var body: some View {
    GlassEffectContainer(spacing: 40.0) {
        HStack(spacing: 40.0) {
            Image(systemName: "scribble.variable")
                .frame(width: 80.0, height: 80.0)
                .font(.system(size: 36))
                .glassEffect()
                .glassEffectID("pencil", in: namespace)

            if isExpanded {
                Image(systemName: "eraser.fill")
                    .frame(width: 80.0, height: 80.0)
                    .font(.system(size: 36))
                    .glassEffect()
                    .glassEffectID("eraser", in: namespace)
            }
        }
    }

    Button("Toggle") {
        withAnimation {
            isExpanded.toggle()
        }
    }
    .buttonStyle(.glass)
}
```

## 使用 Liquid Glass 效果时优化性能

创建过多的 Liquid Glass 效果容器，以及将过多效果应用于容器外的视图，都可能降低性能。请限制屏幕上同时使用的 Liquid Glass 效果数量。此外，还要优化应用在用户使用时的渲染时间。要了解如何提升 UI 性能，请参阅 [https://developer.apple.com/videos/play/tech-talks/10855/] 和 [https://developer.apple.com/videos/play/wwdc2025/306/]。

## 使用 Liquid Glass 设置视图样式

- **里程碑：使用 Liquid Glass 构建应用**：使用系统提供的和自定义的 Liquid Glass 增强应用体验。

- **glassEffect(_:in:)**：将 Liquid Glass 效果应用于视图。

- **interactive(_:)**：返回配置为交互式的结构副本。

- **GlassEffectContainer**：将多个液态玻璃形状合并为一个单一形状的视图，该单一形状可以相互变形。

- **GlassEffectTransition**：描述在视图层次结构中添加或移除玻璃效果时要应用的更改的结构。

- **GlassButtonStyle**：根据按钮上下文应用玻璃边框图案的按钮样式。

- **GlassProminentButtonStyle**：根据按钮上下文应用醒目玻璃边框图案的按钮样式。

- **DefaultGlassEffectShape**：玻璃效果应用的默认形状，即胶囊体。


---
source: https://developer.apple.com/documentation/SwiftUI/Applying-Liquid-Glass-to-custom-views
crawled: 2025-12-02T17:02:03Z
---

# Applying Liquid Glass to custom views

**Article**

Configure, combine, and morph views using Liquid Glass effects.

## Overview

Interfaces across Apple platforms feature a new dynamic material called Liquid Glass, which combines the optical properties of glass with a sense of fluidity. Liquid Glass is a material that blurs content behind it, reflects color and light of surrounding content, and reacts to touch and pointer interactions in real time. Standard components in SwiftUI use Liquid Glass. Adopt Liquid Glass on custom components to move, combine, and morph them into one another with unique animations and transitions.



To learn about Liquid Glass and more, see [Landmarks-Building-an-app-with-Liquid-Glass](Landmarks-Building-an-app-with-Liquid-Glass.zh-Hans.md).

## Apply and configure Liquid Glass effects

Use the [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) modifier to add Liquid Glass effects to a view. By default, the modifier uses the [regular](Glass/regular.zh-Hans.md) variant of [Glass](Glass.zh-Hans.md) and applies the given effect within a [Capsule](Capsule.zh-Hans.md) shape behind the view’s content.

Configure the effect to customize your components in a variety of ways:

- Use different shapes to have a consistent look and feel across custom components in your app. For example, use a rounded rectangle if you’re applying the effect to larger components that would look odd as a `Capsule` or [Circle](Circle.zh-Hans.md).
- Assign a tint color to suggest prominence.
- Add [interactive(_:)](Glass/interactive.zh-Hans.md) to custom components to make them react to touch and pointer interactions. This applies the same responsive and fluid reactions that [glass](PrimitiveButtonStyle/glass.zh-Hans.md) provides to standard buttons.

In the examples below, observe how to apply Liquid Glass effects to a view, use an alternate shape with a specific corner radius, and create a tinted view that responds to interactivity:



```swift
Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect()

Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect(in: .rect(cornerRadius: 16.0))

Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect(.regular.tint(.orange).interactive())
```

## Combine multiple views with Liquid Glass containers

Use [GlassEffectContainer](GlassEffectContainer.zh-Hans.md) when applying Liquid Glass effects on multiple views to achieve the best rendering performance. A container also allows views with Liquid Glass effects to blend their shapes together and to morph in and out of each other during transitions. Inside a container, each view with the [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) modifier renders with the effects behind it.

Customize the spacing on the container to control how the Liquid Glass effects behind views interact with one another. The larger the spacing value on the container, the sooner the Liquid Glass effects behind views blend together and merge the shapes during a transition. A spacing value on the container that’s larger than the spacing of an interior [HStack](HStack.zh-Hans.md), [VStack](VStack.zh-Hans.md), or other layout container causes Liquid Glass effects to blend together at rest because the views are too close to each other. Animating views in or out causes the shapes to morph apart or together as the space in the container changes.

The `glassEffect(_:in:)` modifier captures the content to send to the container to render. Apply the `glassEffect(_:in:)` modifier after other modifiers that affect the appearance of the view.

In the example below, two images are placed close to each other and the Liquid Glass effects begin to blend their shapes together. This creates a fluid animation as components move around each other within a container:



```swift
GlassEffectContainer(spacing: 40.0) {
    HStack(spacing: 40.0) {
        Image(systemName: "scribble.variable")
            .frame(width: 80.0, height: 80.0)
            .font(.system(size: 36))
            .glassEffect()

        Image(systemName: "eraser.fill")
            .frame(width: 80.0, height: 80.0)
            .font(.system(size: 36))
            .glassEffect()

            // An `offset` shows how Liquid Glass effects react to each other in a container.
            // Use animations and components appearing and disappearing to obtain effects that look purposeful.
            .offset(x: -40.0, y: 0.0)
    }
}
```

In some cases, you want the geometries of multiple views to contribute to a single Liquid Glass effect capsule, even when your content is at rest. Use the [glassEffectUnion(id:namespace:)](View/glassEffectUnion_id_namespace.zh-Hans.md) modifier to specify that a view contributes to a unified effect with a particular ID. This combines all effects with a similar shape, Liquid Glass effect, and ID into a single shape with the applied Liquid Glass material. This is especially useful when creating views dynamically, or with views that live outside of a layout container, like an `HStack` or `VStack`.



```swift
let symbolSet: [String] = ["cloud.bolt.rain.fill", "sun.rain.fill", "moon.stars.fill", "moon.fill"]

GlassEffectContainer(spacing: 20.0) {
    HStack(spacing: 20.0) {
        ForEach(symbolSet.indices, id: \.self) { item in
            Image(systemName: symbolSet[item])
                .frame(width: 80.0, height: 80.0)
                .font(.system(size: 36))
                .glassEffect()
                .glassEffectUnion(id: item < 2 ? "1" : "2", namespace: namespace)
        }
    }
}
```

## Morph Liquid Glass effects during transitions

Morphing effects occur during transitions or animations between views with Liquid Glass effects. Coordinate transitions between views with effects in a container by using the [glassEffectID(_:in:)](View/glassEffectID___in.zh-Hans.md) modifier. [GlassEffectTransition](GlassEffectTransition.zh-Hans.md) allows you to specify the type of transition to use when you want to add or remove effects within a container. For effects you want to add or remove that are positioned within the container’s assigned spacing, the default transition type is [matchedGeometry](GlassEffectTransition/matchedGeometry.zh-Hans.md).

If you prefer to have a simpler transition or to create a custom transition, use the [materialize](GlassEffectTransition/materialize.zh-Hans.md) transition and [withAnimation(_:_:)](withAnimation.zh-Hans.md). Use the `materialize` transition for effects you want to add or remove that are farther from each other than the container’s assigned spacing. To provide people with a consistent experience, use `matchedGeometry` and `materialize` transitions across your apps. The system applies more than opacity changes with the available transition types.

Associate each Liquid Glass effect with a unique identifier within a namespace that the [Namespace](Namespace.zh-Hans.md) property wrapper provides. These IDs ensure SwiftUI animates the same shapes correctly when a shape appears or disappears due to view hierarchy changes. SwiftUI uses the spacing provided to the effect container along with the geometry of the shapes themselves to determine when and which appropriate shapes to morph into and out of.

The `glassEffectID(_:in:)` and `glassEffectTransition(_:)` modifiers only affect their content during view hierarchy transitions or animations.

In the example below, the eraser image transitions into and out of the pencil image when the `isExpanded` variable changes. The `GlassEffectContainer` has a spacing value of `40.0`, and the `HStack` within it has a spacing of `40.0`. This morphs the eraser image into the pencil image when the eraser’s nearest edge is less than or equal to the container’s spacing.



```swift
@State private var isExpanded: Bool = false
@Namespace private var namespace

var body: some View {
    GlassEffectContainer(spacing: 40.0) {
        HStack(spacing: 40.0) {
            Image(systemName: "scribble.variable")
                .frame(width: 80.0, height: 80.0)
                .font(.system(size: 36))
                .glassEffect()
                .glassEffectID("pencil", in: namespace)

            if isExpanded {
                Image(systemName: "eraser.fill")
                    .frame(width: 80.0, height: 80.0)
                    .font(.system(size: 36))
                    .glassEffect()
                    .glassEffectID("eraser", in: namespace)
            }
        }
    }

    Button("Toggle") {
        withAnimation {
            isExpanded.toggle()
        }
    }
    .buttonStyle(.glass)
}
```

## Optimize performance when using Liquid Glass effects

Creating too many Liquid Glass effect containers and applying too many effects to views outside of containers can degrade performance. Limit the use of Liquid Glass effects onscreen at the same time. Additionally, optimize how your app spends rendering time as people use it. To learn how to improve the performance of your UI, see [https://developer.apple.com/videos/play/tech-talks/10855/] and [https://developer.apple.com/videos/play/wwdc2025/306/].

## Styling views with Liquid Glass

- **Landmarks: Building an app with Liquid Glass**: Enhance your app experience with system-provided and custom Liquid Glass.
- **glassEffect(_:in:)**: Applies the Liquid Glass effect to a view.
- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **GlassEffectContainer**: A view that combines multiple Liquid Glass shapes into a single shape that can morph individual shapes into one another.
- **GlassEffectTransition**: A structure that describes changes to apply when a glass effect is added or removed from the view hierarchy.
- **GlassButtonStyle**: A button style that applies glass border artwork based on the button’s context.
- **GlassProminentButtonStyle**: A button style that applies prominent glass border artwork based on the button’s context.
- **DefaultGlassEffectShape**: The default shape applied by glass effects, a capsule.

