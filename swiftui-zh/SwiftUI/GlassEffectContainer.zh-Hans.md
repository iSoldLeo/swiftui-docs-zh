--- 来源：https://developer.apple.com/documentation/SwiftUI/GlassEffectContainer
抓取时间：2025-12-02T17:27:11Z

---

# GlassEffectContainer

**Structure**

一个将多个液态玻璃形状组合成一个单一形状的视图，该单一形状可以相互融合。

## 声明

```swift
@MainActor @preconcurrency struct GlassEffectContainer<Content> where Content : View
```

## 概述

使用带有 [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) 修饰符的容器。每个带有液态玻璃效果的视图都会向一组形状贡献一个使用该效果渲染的形状。SwiftUI 会将这些效果一起渲染，从而提高渲染性能，并允许这些效果相互交互和融合。

通过自定义容器的默认间距值来配置形状之间的交互方式。当形状彼此靠近时，它们的路径会开始相互融合。间距越大，形状彼此靠近时混合效果开始得越快。

## 初始化器

- **init(spacing:content:)**：使用指定的间距创建一个玻璃效果容器，并从提供的内容中提取玻璃形状。

## 使用 Liquid Glass 设置视图样式

- **将 Liquid Glass 应用于自定义视图**：使用 Liquid Glass 效果配置、组合和变形视图。

- **里程碑：使用 Liquid Glass 构建应用**：使用系统提供的和自定义的 Liquid Glass 增强您的应用体验。

- **glassEffect(_:in:)**：将 Liquid Glass 效果应用于视图。

- **interactive(_:)**：返回配置为交互式的结构副本。

- **GlassEffectTransition**：描述在视图层次结构中添加或移除玻璃效果时要应用的更改的结构。

- **GlassButtonStyle**：一种按钮样式，可根据按钮的上下文应用玻璃边框效果。

- **GlassProminentButtonStyle**：一种按钮样式，可根据按钮的上下文应用醒目的玻璃边框效果。

- **DefaultGlassEffectShape**：玻璃效果应用的默认形状，即胶囊体。

## 符合以下规范

- Sendable

- SendableMetatype

- View


---
source: https://developer.apple.com/documentation/SwiftUI/GlassEffectContainer
crawled: 2025-12-02T17:27:11Z
---

# GlassEffectContainer

**Structure**

A view that combines multiple Liquid Glass shapes into a single shape that can morph individual shapes into one another.

## Declaration

```swift
@MainActor @preconcurrency struct GlassEffectContainer<Content> where Content : View
```

## Overview

Use a container with the [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) modifier. Each view with a Liquid Glass effect contributes a shape rendered with the effect to a set of shapes. SwiftUI renders the effects together, improving rendering performance and allowing the effects to interact with and morph into one another.

Configure how shapes interact with one another by customizing the default spacing value of the container. As shapes near one another, their paths start to blend into one another. The higher the spacing, the sooner blending begins as the shapes approach each other.

## Initializers

- **init(spacing:content:)**: Creates a glass effect container with the provided spacing, extracting glass shapes from the provided content.

## Styling views with Liquid Glass

- **Applying Liquid Glass to custom views**: Configure, combine, and morph views using Liquid Glass effects.
- **Landmarks: Building an app with Liquid Glass**: Enhance your app experience with system-provided and custom Liquid Glass.
- **glassEffect(_:in:)**: Applies the Liquid Glass effect to a view.
- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **GlassEffectTransition**: A structure that describes changes to apply when a glass effect is added or removed from the view hierarchy.
- **GlassButtonStyle**: A button style that applies glass border artwork based on the button’s context.
- **GlassProminentButtonStyle**: A button style that applies prominent glass border artwork based on the button’s context.
- **DefaultGlassEffectShape**: The default shape applied by glass effects, a capsule.

## Conforms To

- Sendable
- SendableMetatype
- View

