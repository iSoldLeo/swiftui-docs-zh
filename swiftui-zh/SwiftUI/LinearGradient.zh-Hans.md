---
来源： https://developer.apple.com/documentation/SwiftUI/LinearGradient
抓取时间： 2025-12-02T17:27:27Z
---

# 线性渐变

**Structure**

线性梯度。

## 声明

```swift
@frozen struct LinearGradient
```

## 概览

梯度沿起点和终点定义的轴应用颜色函数。梯度会将单位空间点映射到每个填充了梯度的形状的边界矩形中。

使用线性渐变作为形状样式时，也可以使用 [linearGradient(_:startPoint:endPoint:)](ShapeStyle/linearGradient___startPoint_endPoint.zh-Hans.md)。

## 创建线性渐变

- **init(gradient:startPoint:endPoint:)**：从基本梯度创建线性梯度。
- **init(colors:startPoint:endPoint:)**：从一组颜色创建线性渐变。
- **init(stops:startPoint:endPoint:)**：从颜色停止点集合创建线性渐变。

## 支持类型

- **AngularGradient**：角度渐变
- **EllipticalGradient**：绘制椭圆的径向渐变。
- **RadialGradient**：径向梯度。
- **Material**：背景材质类型。
- **ImagePaint**：形状样式，通过重复图像的某个区域来填充形状。
- **HierarchicalShapeStyle**：映射到编号内容样式之一的形状样式。
- **HierarchicalShapeStyleModifier**：可应用于分层形状的样式。
- **ForegroundStyle**：当前上下文中的前景样式。
- **BackgroundStyle**：当前上下文中的背景样式。
- **SelectionShapeStyle**：当前上下文中的背景样式：用于按照平台常规颜色和行为直观表示选择的样式。
- **SeparatorShapeStyle**：适合前景分隔线或边界线的样式。
- **TintShapeStyle**：反映当前色调颜色的样式。
- **FillShapeStyle**：显示其中一种叠加填充的形状样式。
- **LinkShapeStyle**：适合链接的样式。
- **PlaceholderTextShapeStyle**：适合链接的样式：适合占位符文本的样式。

## 符合

- 可发送
- 可发送元类型
- 形状样式
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/LinearGradient
crawled: 2025-12-02T17:27:27Z
---

# LinearGradient

**Structure**

A linear gradient.

## Declaration

```swift
@frozen struct LinearGradient
```

## Overview

The gradient applies the color function along an axis, as defined by its start and end points. The gradient maps the unit space points into the bounding rectangle of each shape filled with the gradient.

When using a linear gradient as a shape style, you can also use [linearGradient(_:startPoint:endPoint:)](ShapeStyle/linearGradient___startPoint_endPoint.zh-Hans.md).

## Creating a linear gradient

- **init(gradient:startPoint:endPoint:)**: Creates a linear gradient from a base gradient.
- **init(colors:startPoint:endPoint:)**: Creates a linear gradient from a collection of colors.
- **init(stops:startPoint:endPoint:)**: Creates a linear gradient from a collection of color stops.

## Supporting types

- **AngularGradient**: An angular gradient.
- **EllipticalGradient**: A radial gradient that draws an ellipse.
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

