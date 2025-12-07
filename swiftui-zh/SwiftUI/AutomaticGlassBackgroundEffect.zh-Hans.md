---
来源： https://developer.apple.com/documentation/SwiftUI/AutomaticGlassBackgroundEffect
抓取时间： 2025-12-02T17:33:43Z
---

# 自动玻璃背景效果

**Structure**

自动玻璃背景效果。

## 声明

```swift
struct AutomaticGlassBackgroundEffect
```

## 概览

您也可以使用 [automatic](GlassBackgroundEffect/automatic.zh-Hans.md) 来构建此效果。

## 初始化器

- **init()**：创建自动玻璃背景效果。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：使用自动玻璃背景效果和与容器相关的圆角矩形形状填充视图背景。
- **glassBackgroundEffect(in:displayMode:)**：使用自动玻璃背景效果和您指定的形状填充视图背景。
- **GlassBackgroundDisplayMode**：玻璃背景的显示模式。
- **GlassBackgroundEffect**：玻璃背景的显示模式：玻璃背景的外观规范。
- **GlassBackgroundEffectConfiguration**：用于构建自定义效果的配置。
- **FeatheredGlassBackgroundEffect**：羽毛状玻璃背景效果。
- **PlateGlassBackgroundEffect**：平板玻璃背景效果。

## 符合

- 玻璃背景效果


---
source: https://developer.apple.com/documentation/SwiftUI/AutomaticGlassBackgroundEffect
crawled: 2025-12-02T17:33:43Z
---

# AutomaticGlassBackgroundEffect

**Structure**

The automatic glass background effect.

## Declaration

```swift
struct AutomaticGlassBackgroundEffect
```

## Overview

You can also use [automatic](GlassBackgroundEffect/automatic.zh-Hans.md) to construct this effect.

## Initializers

- **init()**: Creates an automatic glass glassBackground effect.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.
- **GlassBackgroundDisplayMode**: The display mode of a glass background.
- **GlassBackgroundEffect**: A specification for the appearance of a glass background.
- **GlassBackgroundEffectConfiguration**: A configuration used to build a custom effect.
- **FeatheredGlassBackgroundEffect**: The feathered glass background effect.
- **PlateGlassBackgroundEffect**: The plate glass background effect.

## Conforms To

- GlassBackgroundEffect

