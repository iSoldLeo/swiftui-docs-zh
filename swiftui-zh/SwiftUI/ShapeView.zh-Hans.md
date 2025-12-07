---
来源： https://developer.apple.com/documentation/SwiftUI/ShapeView
抓取时间： 2025-12-02T17:26:34Z
---

# ShapeView

**Protocol**

提供可用于绘图操作的形状的视图。

## 声明

```swift
protocol ShapeView<Content> : View, _RemoveGlobalActorIsolation
```

## 概览

将此类型与 [Shape](Shape.zh-Hans.md) 上的绘制方法一起使用，可对一个形状应用多个填充和/或描边。例如，以下代码会对一个胶囊形状应用填充和描边：

```swift
Capsule()
    .fill(.yellow)
    .stroke(.blue, lineWidth: 8)
```

## 获取形状

- **shape**：该类型绘制的形状，并为其他绘制操作提供形状。
- **Content**：该类型可提供的形状类型。

## 修改形状

- **fill(_:style:)**：用颜色或渐变填充此形状。
- **stroke(_:style:antialiased:)**：用颜色或渐变描边该形状的轮廓。
- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变描画此形状的轮廓。
- **strokeBorder(_:style:antialiased:)**：返回将此视图嵌入其样式线宽一半的视图。
- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是用您提供的内容填充该视图内划的结果。

## 定义形状行为

- **Shape**：绘制视图时可以使用的 2D 形状。
- **AnyShape**：经过类型化的形状值。
- **ShapeRole**：形状的造型方法。
- **StrokeStyle**：描画路径的笔画特征。
- **StrokeShapeView**：对形状进行描边的形状提供者。
- **StrokeBorderShapeView**：会描边的形状提供程序。
- **FillStyle**：用于光栅化矢量形状的样式。
- **FillShapeView**：填充形状的形状提供程序。

## 继承自

- 查看

## 符合类型

- 填充形状视图
- 描边形状视图
- 描边形状视图


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeView
crawled: 2025-12-02T17:26:34Z
---

# ShapeView

**Protocol**

A view that provides a shape that you can use for drawing operations.

## Declaration

```swift
protocol ShapeView<Content> : View, _RemoveGlobalActorIsolation
```

## Overview

Use this type with the drawing methods on [Shape](Shape.zh-Hans.md) to apply multiple fills and/or strokes to a shape. For example, the following code applies a fill and stroke to a capsule shape:

```swift
Capsule()
    .fill(.yellow)
    .stroke(.blue, lineWidth: 8)
```

## Getting the shape

- **shape**: The shape that this type draws and provides for other drawing operations.
- **Content**: The type of shape this can provide.

## Modify the shape

- **fill(_:style:)**: Fills this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **strokeBorder(_:style:antialiased:)**: Returns a view that’s the result of insetting this view by half of its style’s line width.
- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that’s the result of filling an inner stroke of this view with the content you supply.

## Defining shape behavior

- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Inherits From

- View

## Conforming Types

- FillShapeView
- StrokeBorderShapeView
- StrokeShapeView

