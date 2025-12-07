---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading
抓取时间： 2025-12-02T20:58:06Z
---

# GraphicsContext.Shading

**Structure**

用于勾画或填充路径的颜色或图案。

## 声明

```swift
struct Shading
```

## 概览

使用着色实例来描述使用[stroke(_:with:style:)](stroke___with_style.zh-Hans.md) 等方法勾勒的路径的颜色或图案，或使用[fill(_:with:style:)](fill___with_style.zh-Hans.md) 方法填充的区域内部的颜色或图案。通过调用`Shading` 结构的工厂方法之一来获取着色实例。您可以将着色基于

- A [Color](../Color.zh-Hans.md)。
- A [Gradient](../Gradient.zh-Hans.md)。
- 符合[ShapeStyle](../ShapeStyle.zh-Hans.md)的任何类型。
- 一个[Image](../Image.zh-Hans.md)。
- 您已经绘制到上下文中的内容。
- 其他着色实例的集合。

## 颜色

- **color(_:)**：返回一个填充颜色的阴影实例。
- **color(_:red:green:blue:opacity:)**：返回在给定颜色空间中填充颜色的着色实例。
- **color(_:white:opacity:)**：返回一个在给定颜色空间中填充单色的着色实例。

## 梯度

- **linearGradient(_:startPoint:endPoint:options:)**：返回一个填充线性（轴向）渐变的阴影实例。
- **radialGradient(_:center:startRadius:endRadius:options:)**：返回一个填充径向渐变的阴影实例。
- **conicGradient(_:center:angle:options:)**：返回一个填充圆锥形（角度）渐变的阴影实例。

## 其他形状样式

- **style(_:)**：返回一个填充给定形状样式的阴影实例。
- **foreground**：使用图形上下文环境中的前景样式填充的着色实例。

## 图像

- **tiledImage(_:origin:sourceRect:scale:)**：返回一个在无限平面上平铺图像的着色实例。

## 复合着色类型

- **palette(_:)**：返回由着色实例数组构建的多级着色实例。
- **backdrop**：绘制当前背景副本的着色实例。

## 使用自定义金属着色器

- **shader(_:bounds:)**：返回一个着色实例，该实例会填充对每个像素的着色器查询结果。

## 类型方法

- **meshGradient(_:)**：返回一个使用网格渐变填充的着色实例。

## 绘制路径

- **stroke(_:with:lineWidth:)**：以指定的线宽在上下文中绘制路径。
- **stroke(_:with:style:)**：以指定的笔画样式在上下文中绘制路径。
- **fill(_:with:style:)**：在上下文中绘制路径并填充轮廓区域。
- **GraphicsContext.GradientOptions**：影响颜色渐变渲染的选项。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading
crawled: 2025-12-02T20:58:06Z
---

# GraphicsContext.Shading

**Structure**

A color or pattern that you can use to outline or fill a path.

## Declaration

```swift
struct Shading
```

## Overview

Use a shading instance to describe the color or pattern of a path that you outline with a method like [stroke(_:with:style:)](stroke___with_style.zh-Hans.md), or of the interior of a region that you fill with the [fill(_:with:style:)](fill___with_style.zh-Hans.md) method. Get a shading instance by calling one of the `Shading` structure’s factory methods. You can base shading on:

- A [Color](../Color.zh-Hans.md).
- A [Gradient](../Gradient.zh-Hans.md).
- Any type that conforms to [ShapeStyle](../ShapeStyle.zh-Hans.md).
- An [Image](../Image.zh-Hans.md).
- What you’ve already drawn into the context.
- A collection of other shading instances.

## Colors

- **color(_:)**: Returns a shading instance that fills with a color.
- **color(_:red:green:blue:opacity:)**: Returns a shading instance that fills with a color in the given color space.
- **color(_:white:opacity:)**: Returns a shading instance that fills with a monochrome color in the given color space.

## Gradients

- **linearGradient(_:startPoint:endPoint:options:)**: Returns a shading instance that fills a linear (axial) gradient.
- **radialGradient(_:center:startRadius:endRadius:options:)**: Returns a shading instance that fills a radial gradient.
- **conicGradient(_:center:angle:options:)**: Returns a shading instance that fills a conic (angular) gradient.

## Other shape styles

- **style(_:)**: Returns a shading instance that fills with the given shape style.
- **foreground**: A shading instance that fills with the foreground style from the graphics context’s environment.

## Images

- **tiledImage(_:origin:sourceRect:scale:)**: Returns a shading instance that tiles an image across the infinite plane.

## Composite shading types

- **palette(_:)**: Returns a multilevel shading instance constructed from an array of shading instances.
- **backdrop**: A shading instance that draws a copy of the current background.

## Using a custom Metal shader

- **shader(_:bounds:)**: Returns a shading instance that fills with the results of querying a shader for each pixel.

## Type Methods

- **meshGradient(_:)**: Returns a shading instance that fills with a mesh gradient.

## Drawing a path

- **stroke(_:with:lineWidth:)**: Draws a path into the context with a specified line width.
- **stroke(_:with:style:)**: Draws a path into the context with a specified stroke style.
- **fill(_:with:style:)**: Draws a path into the context and fills the outlined region.
- **GraphicsContext.GradientOptions**: Options that affect the rendering of color gradients.

## Conforms To

- Sendable
- SendableMetatype

