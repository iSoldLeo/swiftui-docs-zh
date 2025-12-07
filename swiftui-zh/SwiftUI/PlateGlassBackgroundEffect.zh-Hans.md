---
来源： https://developer.apple.com/documentation/SwiftUI/PlateGlassBackgroundEffect
抓取时间： 2025-12-02T17:33:45Z
---

# PlateGlassBackgroundEffect

**Structure**

平板玻璃背景效果。

## 声明

```swift
struct PlateGlassBackgroundEffect
```

## 概览

您也可以使用 [plate](GlassBackgroundEffect/plate.zh-Hans.md) 来构建此效果。

## 初始化器

- **init()**：创建平板玻璃背景效果。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：使用自动玻璃背景效果和容器相关的圆角矩形形状填充视图背景。
- **glassBackgroundEffect(in:displayMode:)**：使用自动玻璃背景效果和您指定的形状填充视图背景。
- **GlassBackgroundDisplayMode**：玻璃背景的显示模式。
- **GlassBackgroundEffect**：玻璃背景的显示模式：玻璃背景的外观规范。
- **AutomaticGlassBackgroundEffect**：自动玻璃背景效果。
- **GlassBackgroundEffectConfiguration**：用于创建自定义效果的配置。
- **FeatheredGlassBackgroundEffect**：羽毛状玻璃背景效果。

## 符合

- 玻璃背景效果


---
source: https://developer.apple.com/documentation/SwiftUI/PlateGlassBackgroundEffect
crawled: 2025-12-02T17:33:45Z
---

# PlateGlassBackgroundEffect

**Structure**

The plate glass background effect.

## Declaration

```swift
struct PlateGlassBackgroundEffect
```

## Overview

You can also use [plate](GlassBackgroundEffect/plate.zh-Hans.md) to construct this effect.

## Initializers

- **init()**: Creates a plate glass glassBackground effect.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.
- **GlassBackgroundDisplayMode**: The display mode of a glass background.
- **GlassBackgroundEffect**: A specification for the appearance of a glass background.
- **AutomaticGlassBackgroundEffect**: The automatic glass background effect.
- **GlassBackgroundEffectConfiguration**: A configuration used to build a custom effect.
- **FeatheredGlassBackgroundEffect**: The feathered glass background effect.

## Conforms To

- GlassBackgroundEffect

