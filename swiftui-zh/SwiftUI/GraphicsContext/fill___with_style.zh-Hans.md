---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/fill(_:with:style:)
抓取时间：2025-12-02T20:58:05Z
---

# fill(_:with:style:)

**实例方法**

在上下文中绘制路径并填充轮廓区域。

## 声明

```swift
func fill(_ path: Path, with shading: GraphicsContext.Shading, style: FillStyle = FillStyle())
```

## 参数

- **path**：要填充区域的轮廓。
- **shading**：填充`path` 边界区域时要使用的颜色或图案。
- **style**：表示路径光栅化方式的样式。

## 讨论

上下文的当前绘制状态定义了完整的绘制操作。例如，当前的变换和剪切形状以及应用于结果的任何样式都会影响最终结果。

## 绘制路径

- **stroke(_:with:lineWidth:)**：以指定的线宽在上下文中绘制路径。
- **stroke(_:with:style:)**：以指定的笔画样式在上下文中绘制路径。
- **GraphicsContext.Shading**：用于勾画或填充路径的颜色或图案。
- **GraphicsContext.GradientOptions**：影响颜色渐变渲染的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/fill(_:with:style:)
crawled: 2025-12-02T20:58:05Z
---

# fill(_:with:style:)

**Instance Method**

Draws a path into the context and fills the outlined region.

## Declaration

```swift
func fill(_ path: Path, with shading: GraphicsContext.Shading, style: FillStyle = FillStyle())
```

## Parameters

- **path**: The outline of the region to fill.
- **shading**: The color or pattern to use when filling the region bounded by `path`.
- **style**: A style that indicates how to rasterize the path.

## Discussion

The current drawing state of the context defines the full drawing operation. For example, the current transformation and clip shapes, and any styles applied to the result, affect the final result.

## Drawing a path

- **stroke(_:with:lineWidth:)**: Draws a path into the context with a specified line width.
- **stroke(_:with:style:)**: Draws a path into the context with a specified stroke style.
- **GraphicsContext.Shading**: A color or pattern that you can use to outline or fill a path.
- **GraphicsContext.GradientOptions**: Options that affect the rendering of color gradients.

