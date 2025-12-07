---
来源： https://developer.apple.com/documentation/SwiftUI/GlassEffectTransition
抓取时间： 2025-12-02T17:32:59Z
---

# GlassEffectTransition

**Structure**

描述在视图层次结构中添加或移除玻璃效果时要应用的更改的结构。

### 声明

```swift
struct GlassEffectTransition
```

## 类型属性

- **identity**：指定无变化的身份转换。
- **matchedGeometry**：返回匹配的几何玻璃效果转换。
- **materialize**：物化玻璃效果过渡，它将淡入或淡出玻璃材质的内容和动画，但不会尝试匹配任何其他玻璃效果的几何图形。

## 使用液体玻璃制作视图样式

- 将 Liquid Glass 应用于自定义视图**：使用 Liquid Glass 效果配置、组合和变形视图。
- **地标：使用 Liquid Glass 构建应用程序**：使用系统提供的和自定义的 Liquid Glass 增强应用程序体验。
- **glassEffect(_:in:)**：在视图中应用 Liquid Glass 效果。
- **interactive(_:)**：返回配置为交互式结构的副本。
- **GlassEffectContainer**：一种视图，可将多个 Liquid Glass 图形合并为一个图形，并可将单个图形相互变形。
- **GlassButtonStyle**：一种按钮样式，可根据按钮的上下文应用玻璃边框图案。
- **GlassProminentButtonStyle**：根据按钮上下文应用突出玻璃边框图案的按钮样式。
- **DefaultGlassEffectShape**：玻璃效果应用的默认形状，即胶囊。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/GlassEffectTransition
crawled: 2025-12-02T17:32:59Z
---

# GlassEffectTransition

**Structure**

A structure that describes changes to apply when a glass effect is added or removed from the view hierarchy.

## Declaration

```swift
struct GlassEffectTransition
```

## Type Properties

- **identity**: The identity transition specifying no changes.
- **matchedGeometry**: Returns the matched geometry glass effect transition.
- **materialize**: The materialize glass effect transition which will fade in content and animate in or out the glass material but will not attempt to match the geometry of any other glass effects.

## Styling views with Liquid Glass

- **Applying Liquid Glass to custom views**: Configure, combine, and morph views using Liquid Glass effects.
- **Landmarks: Building an app with Liquid Glass**: Enhance your app experience with system-provided and custom Liquid Glass.
- **glassEffect(_:in:)**: Applies the Liquid Glass effect to a view.
- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **GlassEffectContainer**: A view that combines multiple Liquid Glass shapes into a single shape that can morph individual shapes into one another.
- **GlassButtonStyle**: A button style that applies glass border artwork based on the button’s context.
- **GlassProminentButtonStyle**: A button style that applies prominent glass border artwork based on the button’s context.
- **DefaultGlassEffectShape**: The default shape applied by glass effects, a capsule.

## Conforms To

- Sendable
- SendableMetatype

