--- 来源：https://developer.apple.com/documentation/SwiftUI/GlassBackgroundDisplayMode

抓取时间：2025-12-02T17:33:41Z

---

# GlassBackgroundDisplayMode

**Enumeration**

玻璃背景的显示模式。

## 声明

```swift
enum GlassBackgroundDisplayMode
```

## 概述

使用此类型的值来指示何时显示通过视图修饰符（例如 [glassBackgroundEffect(displayMode:)](View/glassBackgroundEffect_displayMode.zh-Hans.md)）添加到视图中的玻璃背景。

## 获取模式

- **GlassBackgroundDisplayMode.always**：始终显示玻璃材质。

- **GlassBackgroundDisplayMode.implicit**：仅当视图尚未包含在玻璃材质中时才显示玻璃材质。

- **GlassBackgroundDisplayMode.never**：从不显示玻璃材质。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：使用自动玻璃背景效果和相对于容器的圆角矩形形状填充视图背景。

- **glassBackgroundEffect(in:displayMode:)**：使用自动玻璃背景效果和您指定的形状填充视图背景。

- **GlassBackgroundEffect**：玻璃背景外观的规范。

- **AutomaticGlassBackgroundEffect**：自动玻璃背景效果。

- **GlassBackgroundEffectConfiguration**：用于构建自定义效果的配置。

- **FeatheredGlassBackgroundEffect**：羽化玻璃背景效果。

- **PlateGlassBackgroundEffect**：平板玻璃背景效果。

## 符合以下标准

- 可复制

- 可等价比较

- 可哈希

- 可发送

- 可发送元数据


---
source: https://developer.apple.com/documentation/SwiftUI/GlassBackgroundDisplayMode
crawled: 2025-12-02T17:33:41Z
---

# GlassBackgroundDisplayMode

**Enumeration**

The display mode of a glass background.

## Declaration

```swift
enum GlassBackgroundDisplayMode
```

## Overview

Use a value of this type to indicate when to display a glass background that you add to a view using a view modifier like [glassBackgroundEffect(displayMode:)](View/glassBackgroundEffect_displayMode.zh-Hans.md).

## Getting the mode

- **GlassBackgroundDisplayMode.always**: Always display the glass material.
- **GlassBackgroundDisplayMode.implicit**: Display the glass material only when the view isn’t already contained in glass.
- **GlassBackgroundDisplayMode.never**: Never display the glass material.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.
- **GlassBackgroundEffect**: A specification for the appearance of a glass background.
- **AutomaticGlassBackgroundEffect**: The automatic glass background effect.
- **GlassBackgroundEffectConfiguration**: A configuration used to build a custom effect.
- **FeatheredGlassBackgroundEffect**: The feathered glass background effect.
- **PlateGlassBackgroundEffect**: The plate glass background effect.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

