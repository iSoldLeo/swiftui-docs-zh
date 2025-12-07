---
来源： https://developer.apple.com/documentation/SwiftUI/GlassProminentButtonStyle
抓取时间：2025-12-02T17:33:00Z
---

# GlassProminentButtonStyle

**Structure**

一种按钮样式，可根据按钮的上下文应用突出的玻璃边框图案。

## 声明

```swift
struct GlassProminentButtonStyle
```

## 概览

您也可以使用 [glassProminent](PrimitiveButtonStyle/glassProminent.zh-Hans.md) 构建这种样式。

## 初始化器

- **init()**：创建一个突出的玻璃按钮样式。

## 实例方法

- **makeBody(configuration:)**：创建表示按钮主体的视图。

## 使用 Liquid Glass 创建视图样式

- 将 Liquid Glass 应用于自定义视图**：使用 Liquid Glass 特效配置、组合和变形视图。
- **地标：使用 Liquid Glass 构建应用程序**：使用系统提供的和自定义的 Liquid Glass 增强应用程序体验。
- **glassEffect(_:in:)**：将 Liquid Glass 效果应用于视图。
- **interactive(_:)**：返回配置为交互式结构的副本。
- **GlassEffectContainer**：将多个 Liquid Glass 图形合并为一个图形的视图，该图形可将单个图形相互变形。
- **GlassEffectTransition**：一种结构，用于描述在视图层次结构中添加或删除玻璃效果时要应用的更改。
- **GlassButtonStyle**：一种按钮样式，可根据按钮的上下文应用玻璃边框美工。
- **DefaultGlassEffectShape**：玻璃效果应用的默认形状，即胶囊。

## 符合

- 原始按钮样式


---
source: https://developer.apple.com/documentation/SwiftUI/GlassProminentButtonStyle
crawled: 2025-12-02T17:33:00Z
---

# GlassProminentButtonStyle

**Structure**

A button style that applies prominent glass border artwork based on the button’s context.

## Declaration

```swift
struct GlassProminentButtonStyle
```

## Overview

You can also use [glassProminent](PrimitiveButtonStyle/glassProminent.zh-Hans.md) to construct this style.

## Initializers

- **init()**: Creates a prominent glass button style.

## Instance Methods

- **makeBody(configuration:)**: Creates a view that represents the body of a button.

## Styling views with Liquid Glass

- **Applying Liquid Glass to custom views**: Configure, combine, and morph views using Liquid Glass effects.
- **Landmarks: Building an app with Liquid Glass**: Enhance your app experience with system-provided and custom Liquid Glass.
- **glassEffect(_:in:)**: Applies the Liquid Glass effect to a view.
- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **GlassEffectContainer**: A view that combines multiple Liquid Glass shapes into a single shape that can morph individual shapes into one another.
- **GlassEffectTransition**: A structure that describes changes to apply when a glass effect is added or removed from the view hierarchy.
- **GlassButtonStyle**: A button style that applies glass border artwork based on the button’s context.
- **DefaultGlassEffectShape**: The default shape applied by glass effects, a capsule.

## Conforms To

- PrimitiveButtonStyle

