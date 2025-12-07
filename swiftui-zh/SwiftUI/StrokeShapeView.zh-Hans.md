---
来源： https://developer.apple.com/documentation/SwiftUI/StrokeShapeView
抓取时间： 2025-12-02T17:27:54Z
---

# StrokeShapeView

**Structure**

形状提供者，可对形状进行描边。

## 声明

```swift
@frozen struct StrokeShapeView<Content, Style, Background> where Content : Shape, Style : ShapeStyle, Background : View
```

## 概览

该类型不是直接创建的，而是 `Shape.stroke` 的返回类型。

## 创建笔划形状视图

- **init(shape:style:strokeStyle:isAntialiased:background:)**：创建描边形状视图。

## 获取形状视图属性

- **background**：该视图下方显示的背景。
- **isAntialiased**：是否要对该形状进行反锯齿绘制。
- **shape**：该类型绘制的形状，并提供给其他绘制操作。
- **strokeStyle**：绘制该视图的形状时使用的描边样式。
- **style**：描边此视图形状的样式。

## 定义形状行为

- **ShapeView**：提供形状的视图，可用于绘图操作。
- **Shape**：绘制视图时可以使用的 2D 形状。
- **AnyShape**：经过类型化的形状值。
- **ShapeRole**：形状的造型方法。
- **StrokeStyle**：描画路径的笔画特征。
- **StrokeBorderShapeView**：对形状的边界进行描边的形状提供程序。
- **FillStyle**：用于光栅化矢量形状的样式。
- **FillShapeView**：填充形状的形状提供程序。

## 符合

- 形状视图
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/StrokeShapeView
crawled: 2025-12-02T17:27:54Z
---

# StrokeShapeView

**Structure**

A shape provider that strokes its shape.

## Declaration

```swift
@frozen struct StrokeShapeView<Content, Style, Background> where Content : Shape, Style : ShapeStyle, Background : View
```

## Overview

You don’t create this type directly; it’s the return type of `Shape.stroke`.

## Creating a stroke shape view

- **init(shape:style:strokeStyle:isAntialiased:background:)**: Create a StrokeShapeView.

## Getting shape view properties

- **background**: The background shown beneath this view.
- **isAntialiased**: Whether this shape should be drawn antialiased.
- **shape**: The shape that this type draws and provides for other drawing operations.
- **strokeStyle**: The stroke style used when stroking this view’s shape.
- **style**: The style that strokes this view’s shape.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Conforms To

- ShapeView
- View

