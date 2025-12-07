---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/FilterOptions
抓取时间： 2025-12-02T20:58:24Z
---

# GraphicsContext.FilterOptions

**Structure**

用于配置添加到图形上下文的过滤器的选项。

## 声明

```swift
@frozen struct FilterOptions
```

## 概览

您可以使用[Filter](Filter.zh-Hans.md) 方法配置应用于[GraphicsContext](../GraphicsContext.zh-Hans.md) 的[addFilter(_:options:)](addFilter___options.zh-Hans.md) 的[Filter](Filter.zh-Hans.md) 过滤器选项。

## 获取过滤器选项

- **linearColor**：使滤波器在线性色彩空间中执行计算的选项。

## 滤色

- **addFilter(_:options:)**：添加适用于后续绘图操作的滤镜。
- **GraphicsContext.Filter**：将图像处理操作应用于渲染内容的类型。
- **GraphicsContext.BlurOptions**：用于配置创建模糊的图形上下文过滤器的选项。
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
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/FilterOptions
crawled: 2025-12-02T20:58:24Z
---

# GraphicsContext.FilterOptions

**Structure**

Options that configure a filter that you add to a graphics context.

## Declaration

```swift
@frozen struct FilterOptions
```

## Overview

You can use filter options to configure a [Filter](Filter.zh-Hans.md) that you apply to a [GraphicsContext](../GraphicsContext.zh-Hans.md) with the [addFilter(_:options:)](addFilter___options.zh-Hans.md) method.

## Getting filter options

- **linearColor**: An option that causes the filter to perform calculations in a linear color space.

## Filtering

- **addFilter(_:options:)**: Adds a filter that applies to subsequent drawing operations.
- **GraphicsContext.Filter**: A type that applies image processing operations to rendered content.
- **GraphicsContext.BlurOptions**: Options that configure the graphics context filter that creates blur.
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

