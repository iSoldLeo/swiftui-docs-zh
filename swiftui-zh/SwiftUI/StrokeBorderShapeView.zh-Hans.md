--- 来源：https://developer.apple.com/documentation/SwiftUI/StrokeBorderShapeView
抓取时间：2025-12-02T17:27:53Z

---

# StrokeBorderShapeView

**Structure**

一个用于描边形状边框的形状提供器。

## 声明

```swift
@frozen struct StrokeBorderShapeView<Content, Style, Background> where Content : InsettableShape, Style : ShapeStyle, Background : View
```

## 概述

您不能直接创建此类型；它是 `Shape.strokeBorder` 的返回类型。

## 创建描边边框形状视图

- **init(shape:style:strokeStyle:isAntialiased:background:)**：创建描边边框形状。

## 获取形状视图属性

- **background**：此视图下方显示的背景。

- **isAntialiased**：此形状是否应启用抗锯齿。

- **shape**：此类型绘制并用于其他绘图操作的形状。

- **strokeStyle**：用于绘制此视图形状的描边样式。

- **style**：用于绘制此视图形状边框的描边样式。

## 定义形状行为

- **ShapeView**：提供可用于绘图操作的形状的视图。

- **Shape**：可用于绘制视图的二维形状。

- **AnyShape**：类型擦除后的形状值。

- **ShapeRole**：形状样式设置方式。

- **StrokeStyle**：描绘路径的笔画特征。

- **StrokeShapeView**：用于描边的形状提供程序。

- **FillStyle**：用于栅格化矢量形状的样式。

- **FillShapeView**：用于填充形状的形状提供程序。

## 符合以下规范

- ShapeView

- View


---
source: https://developer.apple.com/documentation/SwiftUI/StrokeBorderShapeView
crawled: 2025-12-02T17:27:53Z
---

# StrokeBorderShapeView

**Structure**

A shape provider that strokes the border of its shape.

## Declaration

```swift
@frozen struct StrokeBorderShapeView<Content, Style, Background> where Content : InsettableShape, Style : ShapeStyle, Background : View
```

## Overview

You don’t create this type directly; it’s the return type of `Shape.strokeBorder`.

## Creating a stroke border shape view

- **init(shape:style:strokeStyle:isAntialiased:background:)**: Create a stroke border shape.

## Getting shape view properties

- **background**: The background shown beneath this view.
- **isAntialiased**: Whether this shape should be drawn antialiased.
- **shape**: The shape that this type draws and provides for other drawing operations.
- **strokeStyle**: The stroke style used when stroking this view’s shape.
- **style**: The style that strokes the border of this view’s shape.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Conforms To

- ShapeView
- View

