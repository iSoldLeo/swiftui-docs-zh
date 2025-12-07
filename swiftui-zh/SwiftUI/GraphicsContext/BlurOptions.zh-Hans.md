---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlurOptions
抓取时间： 2025-12-02T20:58:25Z
---

# GraphicsContext.BlurOptions

**Structure**

用于配置创建模糊的图形上下文过滤器的选项。

## 声明

```swift
@frozen struct BlurOptions
```

## 概览

当您调用[blur(radius:options:)](Filter/blur_radius_options.zh-Hans.md) 创建[Filter](Filter.zh-Hans.md) 时，可以使用一组这些选项来为绘制到[GraphicsContext](../GraphicsContext.zh-Hans.md) 中的对象添加模糊效果。

## 获取模糊选项

- **dithersResult**：使滤波器产生抖动效果以减少条带的选项。
- **opaque**：使滤波器确保结果完全不透明的选项。

## 滤波

- **addFilter(_:options:)**：添加适用于后续绘图操作的过滤器。
- **GraphicsContext.Filter**：将图像处理操作应用于渲染内容的类型。
- **GraphicsContext.FilterOptions**：用于配置添加到图形上下文的过滤器的选项。
- **GraphicsContext.ShadowOptions**：配置创建阴影的图形上下文过滤器的选项。

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
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlurOptions
crawled: 2025-12-02T20:58:25Z
---

# GraphicsContext.BlurOptions

**Structure**

Options that configure the graphics context filter that creates blur.

## Declaration

```swift
@frozen struct BlurOptions
```

## Overview

You can use a set of these options when you call [blur(radius:options:)](Filter/blur_radius_options.zh-Hans.md) to create a [Filter](Filter.zh-Hans.md) that adds blur to an object that you draw into a [GraphicsContext](../GraphicsContext.zh-Hans.md).

## Getting blur options

- **dithersResult**: An option that causes the filter to dither the result, to reduce banding.
- **opaque**: An option that causes the filter to ensure the result is completely opaque.

## Filtering

- **addFilter(_:options:)**: Adds a filter that applies to subsequent drawing operations.
- **GraphicsContext.Filter**: A type that applies image processing operations to rendered content.
- **GraphicsContext.FilterOptions**: Options that configure a filter that you add to a graphics context.
- **GraphicsContext.ShadowOptions**: Options that configure the graphics context filter that creates shadows.

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

