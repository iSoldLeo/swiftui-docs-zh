---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/stroke(_:with:style:)
抓取时间： 2025-12-01T00:42:13Z
---

# stroke(_:with:style:)

**实例方法**

使用指定的描边样式在上下文中绘制路径。

## 声明

```swift
func stroke(_ path: Path, with shading: GraphicsContext.Shading, style: StrokeStyle)
```

## 参数

- **path**：要勾画的路径。
- **shading**：勾画 `path` 时要使用的颜色或图案。
- **style**：表示如何勾画路径轮廓的样式。

## 讨论

如果只需要控制样式的 [lineWidth](../StrokeStyle/lineWidth.zh-Hans.md) 属性，请使用 [stroke(_:with:lineWidth:)](stroke___with_lineWidth.zh-Hans.md) 代替。

## 绘制路径

- **stroke(_:with:lineWidth:)**：以指定的线宽在上下文中绘制路径。
- **fill(_:with:style:)**：在上下文中绘制路径并填充轮廓区域。
- **GraphicsContext.Shading**：用于勾画或填充路径的颜色或图案。
- **GraphicsContext.GradientOptions**：影响颜色渐变渲染的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/stroke(_:with:style:)
crawled: 2025-12-01T00:42:13Z
---

# stroke(_:with:style:)

**Instance Method**

Draws a path into the context with a specified stroke style.

## Declaration

```swift
func stroke(_ path: Path, with shading: GraphicsContext.Shading, style: StrokeStyle)
```

## Parameters

- **path**: The path to outline.
- **shading**: The color or pattern to use when outlining the `path`.
- **style**: A style that indicates how to outline the path.

## Discussion

If you only need to control the style’s [lineWidth](../StrokeStyle/lineWidth.zh-Hans.md) property, use [stroke(_:with:lineWidth:)](stroke___with_lineWidth.zh-Hans.md) instead.

## Drawing a path

- **stroke(_:with:lineWidth:)**: Draws a path into the context with a specified line width.
- **fill(_:with:style:)**: Draws a path into the context and fills the outlined region.
- **GraphicsContext.Shading**: A color or pattern that you can use to outline or fill a path.
- **GraphicsContext.GradientOptions**: Options that affect the rendering of color gradients.

