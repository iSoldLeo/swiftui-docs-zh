---
来源： https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffect
抓取时间： 2025-12-02T17:33:42Z
---

# GlassBackgroundEffect

**Protocol**

玻璃背景外观规范。

## 声明

```swift
protocol GlassBackgroundEffect
```

## 关联类型

- **Body**：代表此特效主体的特效类型。创建自定义特效时，Swift 会根据您对所需 [makeBody(configuration:)](GlassBackgroundEffect/makeBody_configuration.zh-Hans.md) 方法的实现推断出该类型。

### 实例方法

- **makeBody(configuration:)**：定义此特效产生的效果。

## 类型别名

- **GlassBackgroundEffect.Configuration**：传递给 `makeBody(configuration:)` 的配置类型。

## 类型属性

- **automatic**：默认的玻璃背景效果，基于玻璃的上下文。
- **feathered**：羽毛背景效果，具有默认填充量和默认软边缘半径尺寸。
- **plate**：平板玻璃背景效果。

### 类型方法

- **feathered(padding:softEdgeRadius:)**：带有自定义填充和软边半径的羽毛背景效果。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：以自动玻璃背景效果和容器相关圆角矩形形状填充视图背景。
- **glassBackgroundEffect(in:displayMode:)**：用自动玻璃背景效果和您指定的形状填充视图背景。
- **GlassBackgroundDisplayMode**：玻璃背景的显示模式。
- **AutomaticGlassBackgroundEffect**：玻璃背景的显示模式：自动玻璃背景效果。
- **GlassBackgroundEffectConfiguration**：自动玻璃背景效果：用于创建自定义效果的配置。
- **FeatheredGlassBackgroundEffect**：羽毛状玻璃背景效果。
- **PlateGlassBackgroundEffect**：平板玻璃背景效果。

## 符合类型

- 自动玻璃背景效果
- 羽化玻璃背景效果
- 平板玻璃背景效果


---
source: https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffect
crawled: 2025-12-02T17:33:42Z
---

# GlassBackgroundEffect

**Protocol**

A specification for the appearance of a glass background.

## Declaration

```swift
protocol GlassBackgroundEffect
```

## Associated Types

- **Body**: The type of effect representing the body of this effect. When you create a custom effect, Swift infers this type from your implementation of the required [makeBody(configuration:)](GlassBackgroundEffect/makeBody_configuration.zh-Hans.md) method.

## Instance Methods

- **makeBody(configuration:)**: Defines the effect produced by this effect.

## Type Aliases

- **GlassBackgroundEffect.Configuration**: The configuration type passed to `makeBody(configuration:)`.

## Type Properties

- **automatic**: The default glass background effect, based on the glass’s context.
- **feathered**: A feathered background effect with default padding amount and default soft edge radiual size.
- **plate**: A plate glass background effect.

## Type Methods

- **feathered(padding:softEdgeRadius:)**: A feathered background effect with custom padding and soft edge radius.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.
- **GlassBackgroundDisplayMode**: The display mode of a glass background.
- **AutomaticGlassBackgroundEffect**: The automatic glass background effect.
- **GlassBackgroundEffectConfiguration**: A configuration used to build a custom effect.
- **FeatheredGlassBackgroundEffect**: The feathered glass background effect.
- **PlateGlassBackgroundEffect**: The plate glass background effect.

## Conforming Types

- AutomaticGlassBackgroundEffect
- FeatheredGlassBackgroundEffect
- PlateGlassBackgroundEffect

