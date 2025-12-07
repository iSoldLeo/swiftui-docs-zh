---
来源： https://developer.apple.com/documentation/SwiftUI/TintShapeStyle
抓取时间： 2025-12-03T04:53:51Z
---

# 色调形状样式

**Structure**

反映当前色调颜色的样式。

## 声明

```swift
struct TintShapeStyle
```

## 概览

您可以使用[tint(_:)](View/tint.zh-Hans.md)修饰符设置着色。如果没有设置明确的着色，着色将从应用程序的重点色中导出。

您也可以使用[tint](ShapeStyle/tint.zh-Hans.md) 来构建这种样式。

## 创建色调形状样式

- **init()**：创建着色形状样式。

## 支持类型

- **AngularGradient**：角度渐变。
- **EllipticalGradient**：绘制椭圆的径向渐变。
- **LinearGradient**：线性梯度。
- **RadialGradient**：径向梯度。
- **Material**：背景材质类型。
- **ImagePaint**：形状样式，通过重复图像的某个区域来填充形状。
- **HierarchicalShapeStyle**：映射到编号内容样式之一的形状样式。
- **HierarchicalShapeStyleModifier**：可应用于分层形状的样式。
- **ForegroundStyle**：当前上下文中的前景样式。
- **BackgroundStyle**：当前上下文中的背景样式。
- **SelectionShapeStyle**：当前上下文中的背景样式：用于按照平台常规颜色和行为直观表示选择的样式。
- **SeparatorShapeStyle**：适合前景分隔线或边界线的样式。
- **FillShapeStyle**：显示其中一种叠加填充的形状样式。
- **LinkShapeStyle**：适合链接的样式。
- **PlaceholderTextShapeStyle**：适合链接的样式：适合占位符文本的样式。

## 符合

- 可发送
- 可发送元类型
- 形状样式


---
source: https://developer.apple.com/documentation/SwiftUI/TintShapeStyle
crawled: 2025-12-03T04:53:51Z
---

# TintShapeStyle

**Structure**

A style that reflects the current tint color.

## Declaration

```swift
struct TintShapeStyle
```

## Overview

You can set the tint color with the [tint(_:)](View/tint.zh-Hans.md) modifier. If no explicit tint is set, the tint is derived from the app’s accent color.

You can also use [tint](ShapeStyle/tint.zh-Hans.md) to construct this style.

## Creating a tint shape style

- **init()**: Creates a tint shape style.

## Supporting types

- **AngularGradient**: An angular gradient.
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
- **FillShapeStyle**: A shape style that displays one of the overlay fills.
- **LinkShapeStyle**: A style appropriate for links.
- **PlaceholderTextShapeStyle**: A style appropriate for placeholder text.

## Conforms To

- Sendable
- SendableMetatype
- ShapeStyle

