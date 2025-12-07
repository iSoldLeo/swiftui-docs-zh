--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyShapeStyle
抓取时间：2025-12-02T17:36:54Z

---

# AnyShapeStyle

**Structure**

一个已去除类型信息的 ShapeStyle 值。

## 声明

```swift
@frozen struct AnyShapeStyle
```

## 创建形状样式

- **init(_:)**：从 `style` 创建实例。

## 设置内容样式

- **border(_:width:)**：为该视图添加指定样式和宽度的边框。

- **foregroundStyle(_:)**：设置视图的前景色元素使用给定的样式。

- **foregroundStyle(_:_:)**：设置子视图中前景样式的主级别和次级别。

- **foregroundStyle(_:_:_:)**：设置前景样式的主级别、次级别和三级。

- **backgroundStyle(_:)**：设置用于渲染视图背景的指定样式。

- **backgroundStyle**：可选样式，设置后会覆盖默认的系统背景样式。

- **ShapeStyle**：用于渲染形状的颜色或图案。

- **Gradient**：颜色渐变，表示为颜色停止点数组，每个停止点都有一个参数化的位置值。

- **MeshGradient**：由二维定位颜色网格定义的二维渐变。

- **AnyGradient**：颜色渐变。

- **ShadowStyle**：渲染阴影时使用的样式。

- **Glass**：定义液态玻璃材质配置的结构。

## 符合以下规范

- Sendable

- SendableMetatype

- ShapeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/AnyShapeStyle
crawled: 2025-12-02T17:36:54Z
---

# AnyShapeStyle

**Structure**

A type-erased ShapeStyle value.

## Declaration

```swift
@frozen struct AnyShapeStyle
```

## Creating a shape style

- **init(_:)**: Create an instance from `style`.

## Styling content

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.
- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **ShapeStyle**: A color or pattern to use when rendering a shape.
- **Gradient**: A color gradient represented as an array of color stops, each having a parametric location value.
- **MeshGradient**: A two-dimensional gradient defined by a 2D grid of positioned colors.
- **AnyGradient**: A color gradient.
- **ShadowStyle**: A style to use when rendering shadows.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

## Conforms To

- Sendable
- SendableMetatype
- ShapeStyle

