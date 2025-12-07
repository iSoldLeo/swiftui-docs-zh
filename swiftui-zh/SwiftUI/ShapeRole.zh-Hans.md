--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeRole
抓取时间：2025-12-02T17:36:45Z

---

# ShapeRole

**Enumeration**

形状样式设置方式。

## 声明

```swift
enum ShapeRole
```

## 获取形状角色

- **ShapeRole.fill**：指示形状样式中 SwiftUI 是否填充该形状。

- **ShapeRole.stroke**：指示形状样式中 SwiftUI 是否为形状路径添加描边。

- **ShapeRole.separator**：指示形状样式中 SwiftUI 是否将该形状用作分隔符。

## 定义形状行为

- **ShapeView**：提供可用于绘图操作的形状的视图。

- **Shape**：可在绘制视图时使用的二维形状。

- **AnyShape**：擦除文本后的形状值。

- **StrokeStyle**：描绘路径的笔画的特征。

- **StrokeShapeView**：描边形状提供程序。

- **StrokeBorderShapeView**：描边形状提供程序。

- **FillStyle**：栅格化矢量形状的样式。

- **FillShapeView**：填充形状的形状提供程序。

## 符合以下标准

- 可复制

- 可等价比较

- 可哈希

- 可发送

- 可发送元数据


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeRole
crawled: 2025-12-02T17:36:45Z
---

# ShapeRole

**Enumeration**

Ways of styling a shape.

## Declaration

```swift
enum ShapeRole
```

## Getting shape roles

- **ShapeRole.fill**: Indicates to the shape’s style that SwiftUI fills the shape.
- **ShapeRole.stroke**: Indicates to the shape’s style that SwiftUI applies a stroke to the shape’s path.
- **ShapeRole.separator**: Indicates to the shape’s style that SwiftUI uses the shape as a separator.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **AnyShape**: A type-erased shape value.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

