---
来源： https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffectConfiguration
抓取时间： 2025-12-02T17:33:44Z
---

# GlassBackgroundEffectConfiguration

**Structure**

用于创建自定义效果的配置。

## 声明

```swift
struct GlassBackgroundEffectConfiguration
```

## 结构

- **GlassBackgroundEffectConfiguration.Content**：玻璃背景上的字体蚀刻内容。

### 实例属性

- **content**：需要玻璃背景的视图。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：以自动玻璃背景效果和容器相关的圆角矩形形状填充视图背景。
- **glassBackgroundEffect(in:displayMode:)**：用自动玻璃背景效果和您指定的形状填充视图背景。
- **GlassBackgroundDisplayMode**：玻璃背景的显示模式。
- **GlassBackgroundEffect**：玻璃背景的显示模式：玻璃背景的外观规范。
- **AutomaticGlassBackgroundEffect**：自动玻璃背景效果。
- **FeatheredGlassBackgroundEffect**：自动玻璃背景效果：羽毛状玻璃背景效果。
- **PlateGlassBackgroundEffect**：平板玻璃背景效果。


---
source: https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffectConfiguration
crawled: 2025-12-02T17:33:44Z
---

# GlassBackgroundEffectConfiguration

**Structure**

A configuration used to build a custom effect.

## Declaration

```swift
struct GlassBackgroundEffectConfiguration
```

## Structures

- **GlassBackgroundEffectConfiguration.Content**: A type-erased content of a glass background.

## Instance Properties

- **content**: A view that requires a glass background.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.
- **GlassBackgroundDisplayMode**: The display mode of a glass background.
- **GlassBackgroundEffect**: A specification for the appearance of a glass background.
- **AutomaticGlassBackgroundEffect**: The automatic glass background effect.
- **FeatheredGlassBackgroundEffect**: The feathered glass background effect.
- **PlateGlassBackgroundEffect**: The plate glass background effect.

