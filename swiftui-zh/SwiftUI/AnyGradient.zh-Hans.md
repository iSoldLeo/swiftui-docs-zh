---
来源： https://developer.apple.com/documentation/SwiftUI/AnyGradient
抓取时间： 2025-12-02T17:36:56Z
---

# AnyGradient

**Structure**

颜色渐变。

## 声明

```swift
@frozen struct AnyGradient
```

## 概览

作为[ShapeStyle](ShapeStyle.zh-Hans.md)使用时，该类型绘制起点为[0.5, 0]、终点为[0.5, 1]的线性梯度。

### 创建梯度

- **init(_:)**：根据指定的梯度创建一个新实例。

## 使用色彩空间

- **colorSpace(_:)**：返回使用指定色彩空间插值的渐变效果。

## 造型内容

- **border(_:width:)**：为该视图添加指定样式和宽度的边框。
- **foregroundStyle(_:)**：使用指定样式设置视图的前景元素。
- **foregroundStyle(_:_:)**：设置子视图中前景样式的主要和次要级别。
- **foregroundStyle(_:_:_:)**：设置前景样式的一级、二级和三级。
- **backgroundStyle(_:)**：设置指定的样式来渲染视图中的背景。
- **backgroundStyle**：可选样式，设置后会覆盖默认系统背景样式。
- **ShapeStyle**：渲染形状时使用的颜色或图案。
- **AnyShapeStyle**：经过类型化的 ShapeStyle 值。
- **Gradient**：颜色渐变，表示为一个色块数组，每个色块都有一个参数位置值。
- **MeshGradient**：由定位颜色的二维网格定义的二维渐变。
- **ShadowStyle**：渲染阴影时使用的样式。
- **Glass**：定义液态玻璃材质配置的结构。

## 符合

- 可复制
- 等价
- 哈希值
- 缩放范围
- 可发送
- 可发送元类型
- 形状样式


---
source: https://developer.apple.com/documentation/SwiftUI/AnyGradient
crawled: 2025-12-02T17:36:56Z
---

# AnyGradient

**Structure**

A color gradient.

## Declaration

```swift
@frozen struct AnyGradient
```

## Overview

When used as a [ShapeStyle](ShapeStyle.zh-Hans.md), this type draws a linear gradient with start-point [0.5, 0] and end-point [0.5, 1].

## Creating a gradient

- **init(_:)**: Creates a new instance from the specified gradient.

## Working with color spaces

- **colorSpace(_:)**: Returns a version of the gradient that will use a specified color space for interpolating between its colors.

## Styling content

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.
- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **ShapeStyle**: A color or pattern to use when rendering a shape.
- **AnyShapeStyle**: A type-erased ShapeStyle value.
- **Gradient**: A color gradient represented as an array of color stops, each having a parametric location value.
- **MeshGradient**: A two-dimensional gradient defined by a 2D grid of positioned colors.
- **ShadowStyle**: A style to use when rendering shadows.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

## Conforms To

- Copyable
- Equatable
- Hashable
- ScaleRange
- Sendable
- SendableMetatype
- ShapeStyle

