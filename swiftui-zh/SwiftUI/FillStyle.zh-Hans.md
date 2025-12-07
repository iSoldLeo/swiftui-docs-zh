---
来源： https://developer.apple.com/documentation/SwiftUI/FillStyle
抓取时间： 2025-12-02T17:36:46Z
---

# 填充样式

**Structure**

用于光栅化矢量形状的样式。

## 声明

```swift
@frozen struct FillStyle
```

## 创建填充样式

- **init(eoFill:antialiased:)**：使用指定的设置创建新的填充样式。

## 设置填充样式属性

- **isEOFilled**：布尔值，表示在渲染形状时是否使用偶数规则。
- **isAntialiased**：布尔值，用于指示是否对形状的边缘应用抗锯齿处理。

## 定义形状行为

- **ShapeView**：提供形状的视图，可用于绘图操作。
- **Shape**：绘制视图时可以使用的 2D 形状。
- **AnyShape**：经过类型化的形状值。
- **ShapeRole**：形状的造型方法。
- **StrokeStyle**：描画路径的笔画特征。
- **StrokeShapeView**：对形状进行描边的形状提供者。
- **StrokeBorderShapeView**：会描边的形状提供程序。
- **FillShapeView**：形状提供程序：填充形状的形状提供程序。

## 符合

- 比特可复制
- 可复制
- 等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/FillStyle
crawled: 2025-12-02T17:36:46Z
---

# FillStyle

**Structure**

A style for rasterizing vector shapes.

## Declaration

```swift
@frozen struct FillStyle
```

## Creating a fill style

- **init(eoFill:antialiased:)**: Creates a new fill style with the specified settings.

## Setting fill style properties

- **isEOFilled**: A Boolean value that indicates whether to use the even-odd rule when rendering a shape.
- **isAntialiased**: A Boolean value that indicates whether to apply antialiasing to the edges of a shape.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillShapeView**: A shape provider that fills its shape.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

