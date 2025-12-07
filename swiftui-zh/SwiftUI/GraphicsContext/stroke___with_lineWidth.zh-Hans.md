---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/stroke(_:with:lineWidth:)
抓取时间： 2025-12-01T00:42:12Z
---

# stroke(_:with:lineWidth:)

**实例方法**

以指定的线宽在上下文中绘制路径。

## 声明

```swift
func stroke(_ path: Path, with shading: GraphicsContext.Shading, lineWidth: CGFloat = 1)
```

## 参数

- **path**：要勾画的路径。
- **shading**：勾画 `path` 时要使用的颜色或图案。
- **lineWidth**：笔划的宽度，默认为 `1`。

### 讨论

调用此方法时，除 [StrokeStyle](../StrokeStyle.zh-Hans.md) 以外的所有 [lineWidth](../StrokeStyle/lineWidth.zh-Hans.md) 属性都将使用默认值。要控制其他样式属性，请使用 [stroke(_:with:style:)](stroke___with_style.zh-Hans.md) 代替。

## 绘制路径

- **stroke(_:with:style:)**：以指定的笔画样式在上下文中绘制路径。
- **fill(_:with:style:)**：在上下文中绘制路径并填充轮廓区域。
- **GraphicsContext.Shading**：用于勾画或填充路径的颜色或图案。
- **GraphicsContext.GradientOptions**：影响颜色渐变渲染的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/stroke(_:with:lineWidth:)
crawled: 2025-12-01T00:42:12Z
---

# stroke(_:with:lineWidth:)

**Instance Method**

Draws a path into the context with a specified line width.

## Declaration

```swift
func stroke(_ path: Path, with shading: GraphicsContext.Shading, lineWidth: CGFloat = 1)
```

## Parameters

- **path**: The path to outline.
- **shading**: The color or pattern to use when outlining the `path`.
- **lineWidth**: The width of the stroke, which defaults to `1`.

## Discussion

When you call this method, all [StrokeStyle](../StrokeStyle.zh-Hans.md) properties other than [lineWidth](../StrokeStyle/lineWidth.zh-Hans.md) take their default values. To control other style properties, use [stroke(_:with:style:)](stroke___with_style.zh-Hans.md) instead.

## Drawing a path

- **stroke(_:with:style:)**: Draws a path into the context with a specified stroke style.
- **fill(_:with:style:)**: Draws a path into the context and fills the outlined region.
- **GraphicsContext.Shading**: A color or pattern that you can use to outline or fill a path.
- **GraphicsContext.GradientOptions**: Options that affect the rendering of color gradients.

