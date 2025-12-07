---
来源： https://developer.apple.com/documentation/SwiftUI/ShadowStyle
抓取时间： 2025-12-02T17:36:57Z
---

# ShadowStyle

**Structure**

渲染阴影时使用的样式。

## 声明

```swift
struct ShadowStyle
```

## 获取阴影样式

- **drop(color:radius:x:y:)**：创建自定义阴影样式。
- **inner(color:radius:x:y:)**：创建自定义内阴影样式。

## 造型内容

- **border(_:width:)**：以指定的样式和宽度为该视图添加边框。
- **foregroundStyle(_:)**：使用指定样式设置视图的前景元素。
- **foregroundStyle(_:_:)**：设置子视图中前景样式的主要和次要级别。
- **foregroundStyle(_:_:_:)**：设置前景样式的一级、二级和三级。
- **backgroundStyle(_:)**：设置指定的样式来渲染视图中的背景。
- **backgroundStyle**：可选样式，设置后会覆盖默认系统背景样式。
- **ShapeStyle**：渲染形状时使用的颜色或图案。
- **AnyShapeStyle**：经过类型化的 ShapeStyle 值。
- **Gradient**：颜色渐变，表示为一个色块数组，每个色块都有一个参数位置值。
- **MeshGradient**：由定位颜色的二维网格定义的二维渐变。
- **AnyGradient**：颜色渐变。
- **Glass**：颜色渐变：定义液态玻璃材质配置的结构。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/ShadowStyle
crawled: 2025-12-02T17:36:57Z
---

# ShadowStyle

**Structure**

A style to use when rendering shadows.

## Declaration

```swift
struct ShadowStyle
```

## Getting shadow styles

- **drop(color:radius:x:y:)**: Creates a custom drop shadow style.
- **inner(color:radius:x:y:)**: Creates a custom inner shadow style.

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
- **AnyGradient**: A color gradient.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

