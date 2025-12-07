---
来源： https://developer.apple.com/documentation/SwiftUI/Gradient
抓取时间： 2025-12-02T17:36:55Z
---

# 梯度

**Structure**

颜色渐变表示为一个色站数组，每个色站都有一个参数位置值。

## 声明

```swift
@frozen struct Gradient
```

## 从颜色中创建渐变

- **init(colors:)**：从颜色数组创建渐变效果。

## 从停止点创建渐变

- **init(stops:)**：从颜色止点数组创建渐变。
- **stops**：色站数组。
- **Gradient.Stop**：渐变中的一个色站。

## 使用色彩空间

- **colorSpace(_:)**：返回使用指定色彩空间插值的渐变效果。
- **Gradient.ColorSpace**：一种在渐变色之间进行插值的方法。

## 造型内容

- **border(_:width:)**：以指定的样式和宽度为该视图添加边框。
- **foregroundStyle(_:)**：使用指定样式设置视图的前景元素。
- **foregroundStyle(_:_:)**：设置子视图中前景样式的主要和次要级别。
- **foregroundStyle(_:_:_:)**：设置前景样式的一级、二级和三级。
- **backgroundStyle(_:)**：设置指定的样式来渲染视图中的背景。
- **backgroundStyle**：可选样式，设置后会覆盖默认系统背景样式。
- **ShapeStyle**：渲染形状时使用的颜色或图案。
- **AnyShapeStyle**：经过类型化的 ShapeStyle 值。
- **MeshGradient**：由定位颜色的二维网格定义的二维渐变。
- **AnyGradient**：颜色渐变。
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
source: https://developer.apple.com/documentation/SwiftUI/Gradient
crawled: 2025-12-02T17:36:55Z
---

# Gradient

**Structure**

A color gradient represented as an array of color stops, each having a parametric location value.

## Declaration

```swift
@frozen struct Gradient
```

## Creating a gradient from colors

- **init(colors:)**: Creates a gradient from an array of colors.

## Creating a gradient from stops

- **init(stops:)**: Creates a gradient from an array of color stops.
- **stops**: The array of color stops.
- **Gradient.Stop**: One color stop in the gradient.

## Working with color spaces

- **colorSpace(_:)**: Returns a version of the gradient that will use a specified color space for interpolating between its colors.
- **Gradient.ColorSpace**: A method of interpolating between the colors in a gradient.

## Styling content

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.
- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **ShapeStyle**: A color or pattern to use when rendering a shape.
- **AnyShapeStyle**: A type-erased ShapeStyle value.
- **MeshGradient**: A two-dimensional gradient defined by a 2D grid of positioned colors.
- **AnyGradient**: A color gradient.
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

