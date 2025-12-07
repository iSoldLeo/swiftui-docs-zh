---
来源： https://developer.apple.com/documentation/swiftui/defaultglasseffectshape
抓取时间： 2025-12-04T11:34:17Z
---

# 默认玻璃效果形状

**Structure**

玻璃效果应用的默认形状，即胶囊。

## 声明

```swift
struct DefaultGlassEffectShape
```

## 概览

您不能直接使用此类型。相反，SwiftUI 会代表您创建此形状，作为[glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) 修改器的默认参数。

## 初始化器

- **init()**

## 使用液体玻璃设计视图样式

- 将 Liquid Glass 应用于自定义视图**：使用 Liquid Glass 特效配置、组合和变形视图。
- **地标：使用Liquid Glass构建应用程序**：使用系统提供的和自定义的 Liquid Glass 增强应用程序体验。
- **glassEffect(_:in:)**：将 Liquid Glass 效果应用于视图。
- **interactive(_:)**：返回配置为交互式结构的副本。
- **GlassEffectContainer**：将多个 Liquid Glass 图形合并为一个图形的视图，该图形可将单个图形相互变形。
- **GlassEffectTransition**：一种结构，用于描述在视图层次结构中添加或删除玻璃效果时要应用的更改。
- **GlassButtonStyle**：一种按钮样式，可根据按钮的上下文应用玻璃边框美工。
- **GlassProminentButtonStyle**：根据按钮上下文应用突出玻璃边框图案的按钮样式。

## 符合

- 可动画
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/swiftui/defaultglasseffectshape
crawled: 2025-12-04T11:34:17Z
---

# DefaultGlassEffectShape

**Structure**

The default shape applied by glass effects, a capsule.

## Declaration

```swift
struct DefaultGlassEffectShape
```

## Overview

You do not use this type directly. Instead, SwiftUI creates this shape on your behalf as the default parameter of the [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) modifier.

## Initializers

- **init()**

## Styling views with Liquid Glass

- **Applying Liquid Glass to custom views**: Configure, combine, and morph views using Liquid Glass effects.
- **Landmarks: Building an app with Liquid Glass**: Enhance your app experience with system-provided and custom Liquid Glass.
- **glassEffect(_:in:)**: Applies the Liquid Glass effect to a view.
- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **GlassEffectContainer**: A view that combines multiple Liquid Glass shapes into a single shape that can morph individual shapes into one another.
- **GlassEffectTransition**: A structure that describes changes to apply when a glass effect is added or removed from the view hierarchy.
- **GlassButtonStyle**: A button style that applies glass border artwork based on the button’s context.
- **GlassProminentButtonStyle**: A button style that applies prominent glass border artwork based on the button’s context.

## Conforms To

- Animatable
- Sendable
- SendableMetatype
- Shape
- View

