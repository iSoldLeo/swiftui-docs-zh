--- 来源：https://developer.apple.com/documentation/SwiftUI/Shader
抓取时间：2025-12-02T17:37:51Z

---

# 着色器

**Structure**

指向 Metal 着色器库中函数的引用，以及其绑定的 uniform 参数值。

## 声明

```swift
struct Shader
```

## 概述

着色器值可用作视图的滤镜效果，请参阅 [colorEffect(_:isEnabled:)](View/colorEffect___isEnabled.zh-Hans.md)、[distortionEffect(_:maxSampleOffset:isEnabled:)](View/distortionEffect___maxSampleOffset_isEnabled.zh-Hans.md) 和 [layerEffect(_:maxSampleOffset:isEnabled:)](View/layerEffect___maxSampleOffset_isEnabled.zh-Hans.md) 函数。

着色器还符合 [ShapeStyle](ShapeStyle.zh-Hans.md) 协议，允许其 MSL 着色器函数提供逐像素颜色，以填充任何形状或文本视图。要使着色器函数能够用作填充图案，其函数签名必须符合以下要求：

```swift
[[ stitchable ]] half4 name(float2 position, args...)
```

其中 `position` 是应用于着色器的像素的用户空间坐标，`args...` 应与绑定到 `shader` 的 uniform 参数兼容。该函数应返回目标颜色空间（通常为扩展 sRGB）中的预乘颜色值。

## 创建着色器

- **init(function:arguments:)**：根据函数和要绑定到该函数的 uniform 参数值创建一个新的着色器。

- **Shader.Argument**：将单个 uniform 参数值传递给着色器函数。

## 获取着色器函数

- **function**：着色器调用的着色器函数。

- **arguments**：传递给着色器函数的统一参数值。

## 配置着色器

- **dithersColor**：对于返回颜色值的着色器函数，返回的颜色值是否添加了抖动噪声，或者只是简单地四舍五入到输出位深度。对于生成平滑渐变的着色器，通常需要抖动来防止结果中出现可见的条带。

## 结构体

- **Shader.UsageType**：使用 `Shader` 进行渲染的不同方式。

## 实例方法

- **compile(as:)**：尝试异步编译着色器函数，以最大程度地减少首次用于渲染时出现卡顿的可能性。

## 访问 Metal 着色器

- **colorEffect(_:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的颜色，作为滤镜效果。

- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的位置，作为几何扭曲效果。

- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于由 `self` 创建的栅格图层，作为滤镜效果。

- **ShaderFunction**：指向 Metal 着色器库中函数的引用。

- **ShaderLibrary**：一个 Metal 着色器库。

## 符合以下规范

- Copyable

- Equatable

- Sendable

- SendableMetatype

- ShapeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/Shader
crawled: 2025-12-02T17:37:51Z
---

# Shader

**Structure**

A reference to a function in a Metal shader library, along with its bound uniform argument values.

## Declaration

```swift
struct Shader
```

## Overview

Shader values can be used as filter effects on views, see the [colorEffect(_:isEnabled:)](View/colorEffect___isEnabled.zh-Hans.md), [distortionEffect(_:maxSampleOffset:isEnabled:)](View/distortionEffect___maxSampleOffset_isEnabled.zh-Hans.md), and [layerEffect(_:maxSampleOffset:isEnabled:)](View/layerEffect___maxSampleOffset_isEnabled.zh-Hans.md) functions.

Shaders also conform to the [ShapeStyle](ShapeStyle.zh-Hans.md) protocol, letting their MSL shader function provide per-pixel color to fill any shape or text view. For a shader function to act as a fill pattern it must have a function signature matching:

```swift
[[ stitchable ]] half4 name(float2 position, args...)
```

where `position` is the user-space coordinates of the pixel applied to the shader, and `args...` should be compatible with the uniform arguments bound to `shader`. The function should return the premultiplied color value in the color space of the destination (typically extended sRGB).

## Creating a shader

- **init(function:arguments:)**: Creates a new shader from a function and the uniform argument values to bind to the function.
- **Shader.Argument**: A single uniform argument value to a shader function.

## Getting the shader function

- **function**: The shader function called by the shader.
- **arguments**: The uniform argument values passed to the shader function.

## Configuring the shader

- **dithersColor**: For shader functions that return color values, whether the returned color has dither noise added to it, or is simply rounded to the output bit-depth. For shaders generating smooth gradients, dithering is usually necessary to prevent visible banding in the result.

## Structures

- **Shader.UsageType**: The different ways in which a `Shader` may be used to render.

## Instance Methods

- **compile(as:)**: Attempts to asynchronously compile a shader function, to minimize the chance of stalling when it is first used for rendering.

## Accessing Metal shaders

- **colorEffect(_:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.
- **ShaderFunction**: A reference to a function in a Metal shader library.
- **ShaderLibrary**: A Metal shader library.

## Conforms To

- Copyable
- Equatable
- Sendable
- SendableMetatype
- ShapeStyle

