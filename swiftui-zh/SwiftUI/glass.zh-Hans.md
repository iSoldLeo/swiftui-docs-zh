---
来源： https://developer.apple.com/documentation/swiftui/glass
抓取时间： 2025-12-04T13:10:47Z
---

# 玻璃

**Structure**

定义液态玻璃材料配置的结构。

## 声明

```swift
struct Glass
```

## 概览

您可以向 [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) 视图修饰符提供液体玻璃变体的实例：

```swift
Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect()
```

您可以使用[GlassEffectContainer](GlassEffectContainer.zh-Hans.md) 将液态玻璃效果组合起来，它支持根据相关视图的几何形状将具有此效果的视图相互变形。

### 实例方法

- **interactive(_:)**：返回配置为交互式结构的副本。
- **tint(_:)**：返回带有配置色调的结构体副本。

### 类型属性

- **clear**：玻璃的透明变体。
- **identity**：玻璃的标识变体。使用时，您的内容不会受到影响，就像没有使用玻璃效果一样。
- **regular**：液态玻璃材质的常规变体。

## 造型内容

- **border(_:width:)**：为该视图添加指定样式和宽度的边框。
- **foregroundStyle(_:)**：使用指定样式设置视图的前景元素。
- **foregroundStyle(_:_:)**：设置子视图中前景样式的主要和次要级别。
- **foregroundStyle(_:_:_:)**：设置前景样式的一级、二级和三级。
- **backgroundStyle(_:)**：设置指定的样式来渲染视图中的背景。
- **backgroundStyle**：可选样式，设置后会覆盖默认系统背景样式。
- **ShapeStyle**：渲染形状时使用的颜色或图案。
- **AnyShapeStyle**：经过类型擦除的 ShapeStyle 值。
- **Gradient**：颜色渐变，表示为一个色块数组，每个色块都有一个参数位置值。
- **MeshGradient**：由定位颜色的二维网格定义的二维渐变。
- **AnyGradient**：颜色渐变。
- **ShadowStyle**：渲染阴影时使用的样式。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/swiftui/glass
crawled: 2025-12-04T13:10:47Z
---

# Glass

**Structure**

A structure that defines the configuration of the Liquid Glass material.

## Declaration

```swift
struct Glass
```

## Overview

You provide instances of a variant of Liquid Glass to the [glassEffect(_:in:)](View/glassEffect___in.zh-Hans.md) view modifier:

```swift
Text("Hello, World!")
    .font(.title)
    .padding()
    .glassEffect()
```

You can combine Liquid Glass effects using a [GlassEffectContainer](GlassEffectContainer.zh-Hans.md), which supports morphing views with this effect into each other based on the geometry of their associated views.

## Instance Methods

- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **tint(_:)**: Returns a copy of the structure with a configured tint color.

## Type Properties

- **clear**: The clear variant of glass.
- **identity**: The identity variant of glass. When applied, your content remains unaffected as if no glass effect was applied.
- **regular**: The regular variant of the Liquid Glass material.

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
- **ShadowStyle**: A style to use when rendering shadows.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

