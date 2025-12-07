--- 来源：https://developer.apple.com/documentation/SwiftUI/ImagePaint
抓取时间：2025-12-03T04:05:56Z

---

# ImagePaint

**Structure**

一种形状样式，通过重复图像区域来填充形状。

## 声明

```swift
@frozen struct ImagePaint
```

## 概述

您也可以使用 [image(_:sourceRect:scale:)](ShapeStyle/image___sourceRect_scale.zh-Hans.md) 来构建此样式。

## 创建图像绘制样式

- **init(image:sourceRect:scale:)**：创建形状填充样式。

## 配置图像绘制样式

- **image**：要绘制的图像。

- **scale**：绘制图像时应用的缩放因子。

- **sourceRect**：定义要绘制的源图像范围的单位空间矩形。

## 支持的类型

- **AngularGradient**：角度渐变。

- **EllipticalGradient**：绘制椭圆的径向渐变。

- **LinearGradient**：线性渐变。

- **RadialGradient**：径向渐变。

- **Material**：背景材质类型。

- **HierarchicalShapeStyle**：映射到编号内容样式之一的形状样式。

- **HierarchicalShapeStyleModifier**：可应用于层级形状的样式。

- **ForegroundStyle**：当前上下文中的前景样式。

- **BackgroundStyle**：当前上下文中的背景样式。

- **SelectionShapeStyle**：用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **SeparatorShapeStyle**：适用于前景分隔符或边框线的样式。

- **TintShapeStyle**：反映当前色调颜色的样式。

- **FillShapeStyle**：显示叠加填充之一的形状样式。

- **LinkShapeStyle**：适用于链接的样式。

- **PlaceholderTextShapeStyle**：适用于占位符文本的样式。

## 符合以下规范

- Sendable

- SendableMetatype

- ShapeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/ImagePaint
crawled: 2025-12-03T04:05:56Z
---

# ImagePaint

**Structure**

A shape style that fills a shape by repeating a region of an image.

## Declaration

```swift
@frozen struct ImagePaint
```

## Overview

You can also use [image(_:sourceRect:scale:)](ShapeStyle/image___sourceRect_scale.zh-Hans.md) to construct this style.

## Creating an image paint style

- **init(image:sourceRect:scale:)**: Creates a shape-filling shape style.

## Configuring the image paint style

- **image**: The image to be drawn.
- **scale**: A scale factor applied to the image while being drawn.
- **sourceRect**: A unit-space rectangle defining how much of the source image to draw.

## Supporting types

- **AngularGradient**: An angular gradient.
- **EllipticalGradient**: A radial gradient that draws an ellipse.
- **LinearGradient**: A linear gradient.
- **RadialGradient**: A radial gradient.
- **Material**: A background material type.
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

