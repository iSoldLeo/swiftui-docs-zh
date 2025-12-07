---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ShadowOptions
抓取时间： 2025-12-02T20:58:26Z
---

# GraphicsContext.ShadowOptions

**Structure**

用于配置创建阴影的图形上下文过滤器的选项。

## 声明

```swift
@frozen struct ShadowOptions
```

## 概览

调用[shadow(color:radius:x:y:blendMode:options:)](Filter/shadow_color_radius_x_y_blendMode_options.zh-Hans.md) 创建[Filter](Filter.zh-Hans.md) 时，您可以使用这些选项集为绘制到[GraphicsContext](../GraphicsContext.zh-Hans.md) 中的对象添加阴影。

## 获取阴影选项

- **disablesGroup**：使滤波器在当前图层中分别合成对象及其阴影的选项。
- **invertsAlpha**：使滤镜反转阴影的 Alpha 值的选项。
- **shadowAbove**：使滤镜将阴影绘制在对象上方而非下方的选项。
- **shadowOnly**：使滤波器只绘制阴影而省略源对象的选项。

## 滤镜

- **addFilter(_:options:)**：添加适用于后续绘制操作的过滤器。
- **GraphicsContext.Filter**：将图像处理操作应用于渲染内容的类型。
- **GraphicsContext.FilterOptions**：用于配置添加到图形上下文的过滤器的选项。
- **GraphicsContext.BlurOptions**：配置创建模糊的图形上下文过滤器的选项。

## 符合

- 比特可复制
- 可复制
- 等价
- 可表达数组原型
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ShadowOptions
crawled: 2025-12-02T20:58:26Z
---

# GraphicsContext.ShadowOptions

**Structure**

Options that configure the graphics context filter that creates shadows.

## Declaration

```swift
@frozen struct ShadowOptions
```

## Overview

You can use a set of these options when you call [shadow(color:radius:x:y:blendMode:options:)](Filter/shadow_color_radius_x_y_blendMode_options.zh-Hans.md) to create a [Filter](Filter.zh-Hans.md) that adds a drop shadow to an object that you draw into a [GraphicsContext](../GraphicsContext.zh-Hans.md).

## Getting shadow options

- **disablesGroup**: An option that causes the filter to composite the object and its shadow separately in the current layer.
- **invertsAlpha**: An option that causes the filter to invert the alpha of the shadow.
- **shadowAbove**: An option that causes the filter to draw the shadow above the object, rather than below it.
- **shadowOnly**: An option that causes the filter to draw only the shadow, and omit the source object.

## Filtering

- **addFilter(_:options:)**: Adds a filter that applies to subsequent drawing operations.
- **GraphicsContext.Filter**: A type that applies image processing operations to rendered content.
- **GraphicsContext.FilterOptions**: Options that configure a filter that you add to a graphics context.
- **GraphicsContext.BlurOptions**: Options that configure the graphics context filter that creates blur.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

