---
来源： https://developer.apple.com/documentation/SwiftUI/StrokeStyle
抓取时间： 2025-12-02T17:36:45Z
---

# StrokeStyle

**Structure**

描画路径的笔触的特征。

## 声明

```swift
@frozen struct StrokeStyle
```

## 创建描边样式

- **init(lineWidth:lineCap:lineJoin:miterLimit:dash:dashPhase:)**：根据给定的组件创建新的描边样式。

## 设置描边样式属性

- **lineWidth**：描边路径的宽度。
- **lineCap**：线条的端点样式。
- **lineJoin**：直线的端点样式：线条的连接类型。
- **miterLimit**：一个阈值，用于确定是否在连接处使用斜面而不是斜切。
- **dash**：用于制作虚线的已涂色和未涂色线段的长度。
- **dashPhase**：虚线开始的位置。

## 定义形状行为

- **ShapeView**：提供形状的视图，可用于绘图操作。
- **Shape**：绘制视图时可以使用的 2D 形状。
- **AnyShape**：经过类型化的形状值。
- **ShapeRole**：形状的造型方法。
- **StrokeShapeView**：会描边的形状提供程序。
- **StrokeBorderShapeView**：会描边的形状提供程序。
- **FillStyle**：用于光栅化矢量形状的样式。
- **FillShapeView**：填充形状的形状提供程序。

## 符合

- 可动画
- 可复制
- 可等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/StrokeStyle
crawled: 2025-12-02T17:36:45Z
---

# StrokeStyle

**Structure**

The characteristics of a stroke that traces a path.

## Declaration

```swift
@frozen struct StrokeStyle
```

## Creating a stroke style

- **init(lineWidth:lineCap:lineJoin:miterLimit:dash:dashPhase:)**: Creates a new stroke style from the given components.

## Setting stroke style properties

- **lineWidth**: The width of the stroked path.
- **lineCap**: The endpoint style of a line.
- **lineJoin**: The join type of a line.
- **miterLimit**: A threshold used to determine whether to use a bevel instead of a miter at a join.
- **dash**: The lengths of painted and unpainted segments used to make a dashed line.
- **dashPhase**: How far into the dash pattern the line starts.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Conforms To

- Animatable
- Copyable
- Equatable
- Sendable
- SendableMetatype

