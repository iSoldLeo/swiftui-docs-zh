---

来源：https://developer.apple.com/documentation/SwiftUI/EllipticalGradient
抓取时间：2025-12-02T17:27:01Z

---

# EllipticalGradient

**Structure**

绘制椭圆的径向渐变。

## 声明

```swift
@frozen struct EllipticalGradient
```

## 概述

该渐变将其坐标空间映射到定义其中心和半径的单位空间正方形，然后拉伸该正方形以填充其边界矩形，也可能将圆形渐变拉伸成椭圆轮廓。

例如，以视图为中心并填充其边界的椭圆渐变：

```swift
EllipticalGradient(gradient: .init(colors: [.red, .yellow]))
```

将椭圆渐变用作形状样式时，您还可以使用 [ellipticalGradient(_:center:startRadiusFraction:endRadiusFraction:)](ShapeStyle/ellipticalGradient___center_startRadiusFraction_endRadiusFraction.zh-Hans.md)。

## 创建椭圆渐变

- **init(gradient:center:startRadiusFraction:endRadiusFraction:)**：创建椭圆渐变。

- **init(colors:center:startRadiusFraction:endRadiusFraction:)**：从一组颜色创建椭圆渐变。

- **init(stops:center:startRadiusFraction:endRadiusFraction:)**：从一组颜色停止点创建椭圆渐变。

## 支持的类型

- **AngularGradient**：角度渐变。

- **LinearGradient**：线性渐变。

- **RadialGradient**：径向渐变。

- **Material**：背景材质类型。

- **ImagePaint**：一种形状样式，通过重复图像区域来填充形状。

- **HierarchicalShapeStyle**：映射到某个编号内容样式的形状样式。

- **HierarchicalShapeStyleModifier**：可应用于层级形状的样式。

- **ForegroundStyle**：当前上下文中的前景色样式。

- **BackgroundStyle**：当前上下文中的背景色样式。

- **SelectionShapeStyle**：用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **SeparatorShapeStyle**：适用于前景色分隔符或边框线的样式。

- **TintShapeStyle**：反映当前色调颜色的样式。

- **FillShapeStyle**：显示某个叠加填充的形状样式。

- **LinkShapeStyle**：适用于链接的样式。

- **PlaceholderTextShapeStyle**：适用于占位符文本的样式。

## 符合以下规范

- Sendable

- SendableMetatype

- ShapeStyle

- View


---
source: https://developer.apple.com/documentation/SwiftUI/EllipticalGradient
crawled: 2025-12-02T17:27:01Z
---

# EllipticalGradient

**Structure**

A radial gradient that draws an ellipse.

## Declaration

```swift
@frozen struct EllipticalGradient
```

## Overview

The gradient maps its coordinate space to the unit space square in which its center and radii are defined, then stretches that square to fill its bounding rect, possibly also stretching the circular gradient to have elliptical contours.

For example, an elliptical gradient centered on the view, filling its bounds:

```swift
EllipticalGradient(gradient: .init(colors: [.red, .yellow]))
```

When using an elliptical gradient as a shape style, you can also use [ellipticalGradient(_:center:startRadiusFraction:endRadiusFraction:)](ShapeStyle/ellipticalGradient___center_startRadiusFraction_endRadiusFraction.zh-Hans.md).

## Creating an elliptical gradient

- **init(gradient:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient.
- **init(colors:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient from a collection of colors.
- **init(stops:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient from a collection of color stops.

## Supporting types

- **AngularGradient**: An angular gradient.
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

