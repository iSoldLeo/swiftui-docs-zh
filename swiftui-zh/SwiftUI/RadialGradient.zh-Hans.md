--- 来源：https://developer.apple.com/documentation/SwiftUI/RadialGradient

抓取时间：2025-12-02T17:27:42Z

---

# RadialGradient

**Structure**

径向渐变。

## 声明

```swift
@frozen struct RadialGradient
```

## 概述

该渐变应用颜色函数，颜色值以中心点为基准，并根据定义的起始半径和结束半径进行缩放。渐变将单位空间中心点映射到填充了该渐变的每个形状的边界矩形中。

当使用径向渐变作为形状样式时，您还可以使用 [radialGradient(_:center:startRadius:endRadius:)](ShapeStyle/radialGradient___center_startRadius_endRadius.zh-Hans.md)。

## 创建径向渐变

- **init(gradient:center:startRadius:endRadius:)**：从基础渐变创建径向渐变。

- **init(colors:center:startRadius:endRadius:)**：从一组颜色创建径向渐变。

- **init(stops:center:startRadius:endRadius:)**：从一组颜色停止点创建径向渐变。

## 支持的类型

- **AngularGradient**：角度渐变。

- **EllipticalGradient**：绘制椭圆的径向渐变。

- **LinearGradient**：线性渐变。

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
source: https://developer.apple.com/documentation/SwiftUI/RadialGradient
crawled: 2025-12-02T17:27:42Z
---

# RadialGradient

**Structure**

A radial gradient.

## Declaration

```swift
@frozen struct RadialGradient
```

## Overview

The gradient applies the color function as the distance from a center point, scaled to fit within the defined start and end radii. The gradient maps the unit space center point into the bounding rectangle of each shape filled with the gradient.

When using a radial gradient as a shape style, you can also use [radialGradient(_:center:startRadius:endRadius:)](ShapeStyle/radialGradient___center_startRadius_endRadius.zh-Hans.md).

## Creating a radial gradient

- **init(gradient:center:startRadius:endRadius:)**: Creates a radial gradient from a base gradient.
- **init(colors:center:startRadius:endRadius:)**: Creates a radial gradient from a collection of colors.
- **init(stops:center:startRadius:endRadius:)**: Creates a radial gradient from a collection of color stops.

## Supporting types

- **AngularGradient**: An angular gradient.
- **EllipticalGradient**: A radial gradient that draws an ellipse.
- **LinearGradient**: A linear gradient.
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

