--- 来源：https://developer.apple.com/documentation/SwiftUI/BackgroundStyle
抓取时间：2025-12-03T04:05:57Z

---

# BackgroundStyle

**Structure**

当前上下文中的背景样式。

## 声明

```swift
@frozen struct BackgroundStyle
```

## 概述

您也可以使用 [background](ShapeStyle/background.zh-Hans.md) 来构造此样式。

## 创建背景样式

- **init()**：创建背景样式实例。

## 支持的类型

- **AngularGradient**：角度渐变。

- **EllipticalGradient**：绘制椭圆的径向渐变。

- **LinearGradient**：线性渐变。

- **RadialGradient**：径向渐变。

- **Material**：背景材质类型。

- **ImagePaint**：一种形状样式，通过重复图像区域来填充形状。

- **HierarchicalShapeStyle**：一种形状样式，映射到编号的内容样式之一。

- **HierarchicalShapeStyleModifier**：可应用于层级形状的样式。

- **ForegroundStyle**：当前上下文中的前景样式。

- **SelectionShapeStyle**：一种样式，用于按照平台约定的颜色和行为以视觉方式指示选中状态。

- **SeparatorShapeStyle**：适用于前景分隔线或边框线的样式。

- **TintShapeStyle**：反映当前色调颜色的样式。

- **FillShapeStyle**：显示叠加填充之一的形状样式。

- **LinkShapeStyle**：适用于链接的样式。

- **PlaceholderTextShapeStyle**：适用于占位符文本的样式。

## 符合以下规范

- BitwiseCopyable

- Copyable

- Sendable

- SendableMetatype

- ShapeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/BackgroundStyle
crawled: 2025-12-03T04:05:57Z
---

# BackgroundStyle

**Structure**

The background style in the current context.

## Declaration

```swift
@frozen struct BackgroundStyle
```

## Overview

You can also use [background](ShapeStyle/background.zh-Hans.md) to construct this style.

## Creating a background style

- **init()**: Creates a background style instance.

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
- **SelectionShapeStyle**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **SeparatorShapeStyle**: A style appropriate for foreground separator or border lines.
- **TintShapeStyle**: A style that reflects the current tint color.
- **FillShapeStyle**: A shape style that displays one of the overlay fills.
- **LinkShapeStyle**: A style appropriate for links.
- **PlaceholderTextShapeStyle**: A style appropriate for placeholder text.

## Conforms To

- BitwiseCopyable
- Copyable
- Sendable
- SendableMetatype
- ShapeStyle

