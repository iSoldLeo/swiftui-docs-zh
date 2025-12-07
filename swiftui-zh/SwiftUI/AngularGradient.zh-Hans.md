---

来源：https://developer.apple.com/documentation/SwiftUI/AngularGradient
抓取时间：2025-12-02T17:26:37Z

---

# AngularGradient

**Structure**

角度渐变。

## 声明

```swift
@frozen struct AngularGradient
```

## 概述

角度渐变也称为“圆锥”渐变。此渐变会根据相对于中心点以及定义的起始角和终止角的角度变化应用颜色函数。如果 `endAngle - startAngle > 2π`，则渐变仅绘制最后一个完整的转弯。如果 `endAngle - startAngle < 2π`，则渐变会使用由渐变位置 1 和 0 定义的颜色填充缺失区域，并在缺失区域的中间位置进行过渡。渐变会将单位空间中心点映射到填充渐变的每个形状的边界矩形中。

当使用角度渐变作为形状样式时，您还可以使用 [angularGradient(_:center:startAngle:endAngle:)](ShapeStyle/angularGradient___center_startAngle_endAngle.zh-Hans.md)、[conicGradient(_:center:angle:)](ShapeStyle/conicGradient___center_angle.zh-Hans.md) 或类似方法。

## 创建完整旋转角度渐变

- **init(gradient:center:angle:)**：创建一个完成完整旋转的圆锥渐变。

- **init(colors:center:angle:)**：创建一个由一组颜色组成的圆锥渐变，该渐变完成完整旋转。

- **init(stops:center:angle:)**：创建一个由一组颜色停止点组成的圆锥渐变，该渐变完成完整旋转。

## 创建部分旋转角度渐变

- **init(gradient:center:startAngle:endAngle:)**：创建一个角度渐变。

- **init(colors:center:startAngle:endAngle:)**：创建一个由一组颜色组成的角度渐变。

- **init(stops:center:startAngle:endAngle:)**：从一组颜色停止点创建角度渐变。

## 支持的类型

- **EllipticalGradient**：绘制椭圆的径向渐变。

- **LinearGradient**：线性渐变。

- **RadialGradient**：径向渐变。

- **Material**：背景材质类型。

- **ImagePaint**：通过重复图像区域填充形状的形状样式。

- **HierarchicalShapeStyle**：映射到编号内容样式之一的形状样式。

- **HierarchicalShapeStyleModifier**：可应用于层级形状的样式。

- **ForegroundStyle**：当前上下文中的前景色样式。

- **BackgroundStyle**：当前上下文中的背景色样式。

- **SelectionShapeStyle**：用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **SeparatorShapeStyle**：适用于前景色分隔符或边框线的样式。

- **TintShapeStyle**：反映当前色调颜色的样式。

- **FillShapeStyle**：显示叠加填充之一的形状样式。

- **LinkShapeStyle**：适用于链接的样式。

- **PlaceholderTextShapeStyle**：适用于占位符文本的样式。

## 符合以下规范

- Sendable

- SendableMetatype

- ShapeStyle

- View


---
source: https://developer.apple.com/documentation/SwiftUI/AngularGradient
crawled: 2025-12-02T17:26:37Z
---

# AngularGradient

**Structure**

An angular gradient.

## Declaration

```swift
@frozen struct AngularGradient
```

## Overview

An angular gradient is also known as a “conic” gradient. This gradient applies the color function as the angle changes, relative to a center point and defined start and end angles. If `endAngle - startAngle > 2π`, the gradient only draws the last complete turn. If `endAngle - startAngle < 2π`, the gradient fills the missing area with the colors defined by gradient locations one and zero, transitioning between the two halfway across the missing area. The gradient maps the unit space center point into the bounding rectangle of each shape filled with the gradient.

When using an angular gradient as a shape style, you can also use [angularGradient(_:center:startAngle:endAngle:)](ShapeStyle/angularGradient___center_startAngle_endAngle.zh-Hans.md), [conicGradient(_:center:angle:)](ShapeStyle/conicGradient___center_angle.zh-Hans.md), or similar methods.

## Creating a full rotation angular gradient

- **init(gradient:center:angle:)**: Creates a conic gradient that completes a full turn.
- **init(colors:center:angle:)**: Creates a conic gradient from a collection of colors that completes a full turn.
- **init(stops:center:angle:)**: Creates a conic gradient from a collection of color stops that completes a full turn.

## Creating a partial rotation angular gradient

- **init(gradient:center:startAngle:endAngle:)**: Creates an angular gradient.
- **init(colors:center:startAngle:endAngle:)**: Creates an angular gradient from a collection of colors.
- **init(stops:center:startAngle:endAngle:)**: Creates an angular gradient from a collection of color stops.

## Supporting types

- **EllipticalGradient**: A radial gradient that draws an ellipse.
- **LinearGradient**: A linear gradient.
- **RadialGradient**: A radial gradient.
- **Material**: A background material type.
- **ImagePaint**: A shape style that fills a shape by repeating a region of an image.
- **HierarchicalShapeStyle**: A shape style that maps to one of the numbered content styles.
- **HierarchicalShapeStyleModifier**: Styles that you can apply to hierarchical shapes.
- **ForegroundStyle**: The foreground style in the current context.
- **BackgroundStyle**: The background style in the current context.
- **SelectionShapeStyle**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **SeparatorShapeStyle**: A style appropriate for foreground separator or border lines.
- **TintShapeStyle**: A style that reflects the current tint color.
- **FillShapeStyle**: A shape style that displays one of the overlay fills.
- **LinkShapeStyle**: A style appropriate for links.
- **PlaceholderTextShapeStyle**: A style appropriate for placeholder text.

## Conforms To

- Sendable
- SendableMetatype
- ShapeStyle
- View

