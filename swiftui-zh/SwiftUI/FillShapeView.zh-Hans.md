--- 来源：https://developer.apple.com/documentation/SwiftUI/FillShapeView
抓取时间：2025-12-02T17:27:02Z

---

# FillShapeView

**Structure**

一个用于填充形状的形状提供程序。

## 声明

```swift
@frozen struct FillShapeView<Content, Style, Background> where Content : Shape, Style : ShapeStyle, Background : View
```

## 概述

您不能直接创建此类型，它是 `Shape.fill` 的返回类型。

## 创建描边形状视图

- **init(shape:style:fillStyle:background:)**：创建一个 FillShapeView。

## 获取形状视图属性

- **background**：此视图下方显示的背景。

- **fillStyle**：填充此视图形状时使用的填充样式。

- **shape**：此类型绘制并用于其他绘图操作的形状。

- **style**：填充此视图形状的样式。

## 定义形状行为

- **ShapeView**：提供可用于绘图操作的形状的视图。

- **Shape**：可在绘制视图时使用的二维形状。

- **AnyShape**：类型擦除后的形状值。

- **ShapeRole**：形状样式设置方式。

- **StrokeStyle**：描边路径的特征。

- **StrokeShapeView**：描边形状的形状提供程序。

- **StrokeBorderShapeView**：一种用于描边形状边缘的形状提供程序。

- **FillStyle**：一种用于栅格化矢量形状的样式。

## 符合以下规范

- ShapeView

- View


---
source: https://developer.apple.com/documentation/SwiftUI/FillShapeView
crawled: 2025-12-02T17:27:02Z
---

# FillShapeView

**Structure**

A shape provider that fills its shape.

## Declaration

```swift
@frozen struct FillShapeView<Content, Style, Background> where Content : Shape, Style : ShapeStyle, Background : View
```

## Overview

You do not create this type directly, it is the return type of `Shape.fill`.

## Creating a stroke shape view

- **init(shape:style:fillStyle:background:)**: Create a FillShapeView.

## Getting shape view properties

- **background**: The background shown beneath this view.
- **fillStyle**: The fill style used when filling this view’s shape.
- **shape**: The shape that this type draws and provides for other drawing operations.
- **style**: The style that fills this view’s shape.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.

## Conforms To

- ShapeView
- View

