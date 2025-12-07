---
来源： https://developer.apple.com/documentation/swiftui/meshgradient
抓取时间： 2025-12-05T21:09:23Z
---

# 网格梯度

**Structure**

由定位颜色的二维网格定义的二维梯度。

## 声明

```swift
struct MeshGradient
```

## 概览

每个顶点都有一个位置、一种颜色和周围的四个贝塞尔控制点（前、上、后、下），它们定义了连接顶点与其四个相邻顶点的切线。(网格边角上的顶点如果相邻顶点少于四个，则忽略其额外的控制点）。控制点可以明确指定，也可以隐含指定。

在渲染时，会创建一串网格状的贝塞尔补丁，顶点的颜色会在每个补丁上进行线性插值，或通过根据相邻点之间的颜色变化情况导出的另一组立方曲线进行插值--后者通常能带来更平滑的颜色过渡。

```swift
MeshGradient(width: 3, height: 3, points: [
    .init(0, 0), .init(0.5, 0), .init(1, 0),
    .init(0, 0.5), .init(0.5, 0.5), .init(1, 0.5),
    .init(0, 1), .init(0.5, 1), .init(1, 1)
], colors: [
    .red, .purple, .indigo,
    .orange, .white, .blue,
    .yellow, .green, .mint
])
```

## 结构

- **MeshGradient.BezierPoint**：梯度网格中的一个位置及其周围的四个贝塞尔控制点。

## 初始化器

- **init(width:height:bezierPoints:colors:background:smoothsColors:colorSpace:)**：创建新的梯度网格，指定为彩色点的二维网格，明确指定贝塞尔控制点。
- **init(width:height:bezierPoints:resolvedColors:background:smoothsColors:colorSpace:)**：创建新的梯度网格，指定为二维网格的彩色点，明确指定贝塞尔控制点，并使用已解析的 sRGB 颜色。
- **init(width:height:locations:colors:background:smoothsColors:colorSpace:)**：创建新的梯度网格，指定为彩色顶点的二维网格。
- **init(width:height:points:colors:background:smoothsColors:colorSpace:)**：以彩色点的二维网格形式创建新的梯度网格。
- **init(width:height:points:resolvedColors:background:smoothsColors:colorSpace:)**：创建一个新的梯度网格，指定为已解析 sRGB 颜色的二维彩色点网格。

### 实例属性

- **background**：背景色，用于填充定义顶点网格外的任何点。
- **colorSpace**：用于插值顶点颜色的颜色空间。
- **colors**：颜色数组。必须包含 `width x height` 元素。
- **height**：网格的高度，即每列的顶点数。
- **locations**：位置数组。必须包含 `width x height` 元素。
- **smoothsColors**：是否对网格中的颜色（而非仅对网格的形状）使用立方（平滑）插值。
- **width**：网格的宽度，即每行的顶点数。

## 枚举

- **MeshGradient.Colors**：颜色数组：颜色数组。
- **MeshGradient.Locations**：二维位置及其控制点的数组。

## 造型内容

- **border(_:width:)**：以指定的样式和宽度为该视图添加边框。
- **foregroundStyle(_:)**：使用指定样式设置视图的前景元素。
- **foregroundStyle(_:_:)**：设置子视图中前景样式的主要和次要级别。
- **foregroundStyle(_:_:_:)**：设置前景样式的一级、二级和三级。
- **backgroundStyle(_:)**：设置指定的样式来渲染视图中的背景。
- **backgroundStyle**：可选样式，设置后会覆盖默认系统背景样式。
- **ShapeStyle**：渲染形状时使用的颜色或图案。
- **AnyShapeStyle**：经过类型擦除的 ShapeStyle 值。
- **Gradient**：颜色渐变，表示为一个色块数组，每个色块都有一个参数位置值。
- **AnyGradient**：颜色渐变。
- **ShadowStyle**：颜色渐变：渲染阴影时使用的样式。
- **Glass**：定义液态玻璃材质配置的结构。

## 符合

- 可复制
- 可等价
- 可发送
- 可发送元类型
- 形状样式
- 查看


---
source: https://developer.apple.com/documentation/swiftui/meshgradient
crawled: 2025-12-05T21:09:23Z
---

# MeshGradient

**Structure**

A two-dimensional gradient defined by a 2D grid of positioned colors.

## Declaration

```swift
struct MeshGradient
```

## Overview

Each vertex has a position, a color and four surrounding Bezier control points (leading, top, trailing, bottom) that define the tangents connecting the vertex with its four neighboring vertices. (Vertices on the corners or edges of the mesh have less than four neighbors, they ignore their extra control points.) Control points may either be specified explicitly or implicitly.

When rendering, a tessellated sequence of Bezier patches are created, and vertex colors are interpolated across each patch, either linearly, or via another set of cubic curves derived from how the colors change between neighbors – the latter typically gives smoother color transitions.

```swift
MeshGradient(width: 3, height: 3, points: [
    .init(0, 0), .init(0.5, 0), .init(1, 0),
    .init(0, 0.5), .init(0.5, 0.5), .init(1, 0.5),
    .init(0, 1), .init(0.5, 1), .init(1, 1)
], colors: [
    .red, .purple, .indigo,
    .orange, .white, .blue,
    .yellow, .green, .mint
])
```

## Structures

- **MeshGradient.BezierPoint**: One location in a gradient mesh, along with the four Bezier control points surrounding it.

## Initializers

- **init(width:height:bezierPoints:colors:background:smoothsColors:colorSpace:)**: Creates a new gradient mesh specified as a 2D grid of colored points, specifying the Bezier control points explicitly.
- **init(width:height:bezierPoints:resolvedColors:background:smoothsColors:colorSpace:)**: Creates a new gradient mesh specified as a 2D grid of colored points, specifying the Bezier control points explicitly, with already-resolved sRGB colors.
- **init(width:height:locations:colors:background:smoothsColors:colorSpace:)**: Creates a new gradient mesh specified as a 2D grid of colored vertices.
- **init(width:height:points:colors:background:smoothsColors:colorSpace:)**: Creates a new gradient mesh specified as a 2D grid of colored points.
- **init(width:height:points:resolvedColors:background:smoothsColors:colorSpace:)**: Creates a new gradient mesh specified as a 2D grid of colored points, with already-resolved sRGB colors.

## Instance Properties

- **background**: The background color, this fills any points outside the defined vertex mesh.
- **colorSpace**: The color space in which to interpolate vertex colors.
- **colors**: The array of colors. Must contain `width x height` elements.
- **height**: The height of the mesh, i.e. the number of vertices per column.
- **locations**: The array of locations. Must contain `width x height` elements.
- **smoothsColors**: Whether cubic (smooth) interpolation should be used for the colors in the mesh (rather than only for the shape of the mesh).
- **width**: The width of the mesh, i.e. the number of vertices per row.

## Enumerations

- **MeshGradient.Colors**: An array of colors.
- **MeshGradient.Locations**: An array of 2D locations and their control points.

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
- **AnyGradient**: A color gradient.
- **ShadowStyle**: A style to use when rendering shadows.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

## Conforms To

- Copyable
- Equatable
- Sendable
- SendableMetatype
- ShapeStyle
- View

