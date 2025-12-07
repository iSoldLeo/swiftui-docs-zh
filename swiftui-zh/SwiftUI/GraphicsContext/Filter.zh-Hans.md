---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter
抓取时间： 2025-12-02T20:58:23Z
---

# GraphicsContext.Filter

**Structure**

对渲染内容进行图像处理操作的类型。

### 声明

```swift
struct Filter
```

## 概览

通过调用`Filter` 结构定义的工厂方法之一，创建并配置可产生图像处理效果（如添加阴影或模糊效果）的滤镜。调用[addFilter(_:options:)](addFilter___options.zh-Hans.md) 方法将滤镜添加到[GraphicsContext](../GraphicsContext.zh-Hans.md) 中。过滤器只会影响添加过滤器后绘制到上下文中的内容。

## 更改亮度和对比度

- **brightness(_:)**：返回应用亮度调整的滤镜。
- **contrast(_:)**：返回应用对比度调整的滤镜。

## 操作颜色

- **saturation(_:)**：返回应用饱和度调整的滤镜。
- **colorInvert(_:)**：返回反转结果颜色的滤镜。
- **colorMultiply(_:)**：返回将每个颜色分量乘以给定颜色的匹配分量的滤波器。
- **hueRotation(_:)**：返回一个应用色调旋转调整的滤镜。
- **grayscale(_:)**：返回应用灰度调整的滤镜。
- **colorMatrix(_:)**：返回乘以给定颜色矩阵的滤波器。

## 添加模糊效果

- **blur(radius:options:)**：返回一个应用高斯模糊的滤镜。

## 添加阴影

- **shadow(color:radius:x:y:blendMode:options:)**：返回一个添加阴影的滤镜。

## 调整不透明度

- **luminanceToAlpha**：返回根据像素亮度设置其不透明度的滤镜。
- **alphaThreshold(min:max:color:)**：返回一个滤波器，在一定范围内将每个像素的 alpha 分量替换为恒定颜色，否则替换为透明度。

## 添加变换

- **projectionTransform(_:)**：返回一个过滤器，用于变换后续图形基元的光栅化形式。

## 使用自定义金属着色器

- **colorShader(_:)**：返回对每个源像素的颜色应用`shader` 的过滤器。
- **distortionShader(_:maxSampleOffset:)**：返回对每个像素的位置应用`shader` 作为几何扭曲效果的滤波器。
- **layerShader(_:maxSampleOffset:)**：返回将`shader` 应用到源图层内容的滤波器。

## 滤波

- **addFilter(_:options:)**：添加适用于后续绘图操作的过滤器。
- **GraphicsContext.FilterOptions**：配置添加到图形上下文的过滤器的选项。
- **GraphicsContext.BlurOptions**：用于配置创建模糊的图形上下文过滤器的选项。
- **GraphicsContext.ShadowOptions**：配置创建阴影的图形上下文过滤器的选项。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter
crawled: 2025-12-02T20:58:23Z
---

# GraphicsContext.Filter

**Structure**

A type that applies image processing operations to rendered content.

## Declaration

```swift
struct Filter
```

## Overview

Create and configure a filter that produces an image processing effect, like adding a drop shadow or a blur effect, by calling one of the factory methods defined by the `Filter` structure. Call the [addFilter(_:options:)](addFilter___options.zh-Hans.md) method to add the filter to a [GraphicsContext](../GraphicsContext.zh-Hans.md). The filter only affects content that you draw into the context after adding the filter.

## Changing brightness and contrast

- **brightness(_:)**: Returns a filter that applies a brightness adjustment.
- **contrast(_:)**: Returns a filter that applies a contrast adjustment.

## Manipulating color

- **saturation(_:)**: Returns a filter that applies a saturation adjustment.
- **colorInvert(_:)**: Returns a filter that inverts the color of their results.
- **colorMultiply(_:)**: Returns a filter that multiplies each color component by the matching component of a given color.
- **hueRotation(_:)**: Returns a filter that applies a hue rotation adjustment.
- **grayscale(_:)**: Returns a filter that applies a grayscale adjustment.
- **colorMatrix(_:)**: Returns a filter that multiplies by a given color matrix.

## Adding blur

- **blur(radius:options:)**: Returns a filter that applies a Gaussian blur.

## Adding a shadow

- **shadow(color:radius:x:y:blendMode:options:)**: Returns a filter that adds a shadow.

## Adjusting opacity

- **luminanceToAlpha**: Returns a filter that sets the opacity of each pixel based on its luminance.
- **alphaThreshold(min:max:color:)**: Returns a filter that replaces each pixel with alpha components within a range by a constant color, or transparency otherwise.

## Adding a transformation

- **projectionTransform(_:)**: Returns a filter that transforms the rasterized form of subsequent graphics primitives.

## Using a custom Metal shader

- **colorShader(_:)**: Returns a filter that applies `shader` to the color of each source pixel.
- **distortionShader(_:maxSampleOffset:)**: Returns a filter that applies `shader` as a geometric distortion effect on the location of each pixel.
- **layerShader(_:maxSampleOffset:)**: Returns a filter that applies `shader` to the contents of the source layer.

## Filtering

- **addFilter(_:options:)**: Adds a filter that applies to subsequent drawing operations.
- **GraphicsContext.FilterOptions**: Options that configure a filter that you add to a graphics context.
- **GraphicsContext.BlurOptions**: Options that configure the graphics context filter that creates blur.
- **GraphicsContext.ShadowOptions**: Options that configure the graphics context filter that creates shadows.

## Conforms To

- Sendable
- SendableMetatype

