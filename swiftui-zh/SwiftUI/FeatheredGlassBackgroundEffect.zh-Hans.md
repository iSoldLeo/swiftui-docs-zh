---

来源：https://developer.apple.com/documentation/SwiftUI/FeatheredGlassBackgroundEffect
抓取时间：2025-12-02T17:33:44Z

---

# FeatheredGlassBackgroundEffect

**Structure**

羽化玻璃背景效果。

## 声明

```swift
struct FeatheredGlassBackgroundEffect
```

## 概述

您也可以使用 [feathered](GlassBackgroundEffect/feathered.zh-Hans.md) 来构建此效果。

带有羽化玻璃背景的视图的布局大小基于内容大小，而不是玻璃背景大小。当玻璃背景被外部容器（例如 VStack 或 HStack）裁剪时，可以通过增加内容大小（例如内容内边距）或使用其内边距参数减小羽化玻璃背景大小来解决。

## 初始化器

- **init()**：创建羽化玻璃背景效果。

- **init(padding:softEdgeRadius:)**：创建羽化玻璃背景效果。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：使用自动玻璃背景效果和相对于容器的圆角矩形形状填充视图背景。

- **glassBackgroundEffect(in:displayMode:)**：使用自动玻璃背景效果和您指定的形状填充视图背景。

- **GlassBackgroundDisplayMode**：玻璃背景的显示模式。

- **GlassBackgroundEffect**：玻璃背景外观的规范。

- **AutomaticGlassBackgroundEffect**：自动玻璃背景效果。

- **GlassBackgroundEffectConfiguration**：用于构建自定义效果的配置。

- **PlateGlassBackgroundEffect**：平板玻璃背景效果。

## 符合以下配置：

- GlassBackgroundEffect


---
source: https://developer.apple.com/documentation/SwiftUI/FeatheredGlassBackgroundEffect
crawled: 2025-12-02T17:33:44Z
---

# FeatheredGlassBackgroundEffect

**Structure**

The feathered glass background effect.

## Declaration

```swift
struct FeatheredGlassBackgroundEffect
```

## Overview

You can also use [feathered](GlassBackgroundEffect/feathered.zh-Hans.md) to construct this effect.

The layout size of a view with feathered glass background is based on the content size instead of the glass background size. When the glass background is clipped by an outer container, such as VStack or HStack, it can be resolved by incrasing content size, such as content padding, or reducing the feathered glass background size with its padding parameter.

## Initializers

- **init()**: Creates a feathered glassBackground effect.
- **init(padding:softEdgeRadius:)**: Creates a feathered glassBackground effect.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.
- **GlassBackgroundDisplayMode**: The display mode of a glass background.
- **GlassBackgroundEffect**: A specification for the appearance of a glass background.
- **AutomaticGlassBackgroundEffect**: The automatic glass background effect.
- **GlassBackgroundEffectConfiguration**: A configuration used to build a custom effect.
- **PlateGlassBackgroundEffect**: The plate glass background effect.

## Conforms To

- GlassBackgroundEffect

