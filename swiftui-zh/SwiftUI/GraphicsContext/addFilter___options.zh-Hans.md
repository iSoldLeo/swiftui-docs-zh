---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/addFilter(_:options:)
抓取时间：2025-12-02T20:58:22Z
---

# addFilter(_:options:)

**实例方法**

添加适用于后续绘图操作的过滤器。

## 声明

```swift
mutating func addFilter(_ filter: GraphicsContext.Filter, options: GraphicsContext.FilterOptions = FilterOptions())
```

## 参数

- **filter**：通过调用[Filter](Filter.zh-Hans.md) 工厂方法之一创建的图形上下文过滤器。
- **options**：[FilterOptions](FilterOptions.zh-Hans.md)中的一组选项，可用于配置过滤器操作。

## 讨论

要使用过滤功能绘图，SwiftUI.Net 会自动生成一个过滤器：

- 将绘制操作栅格化到隐式透明图层，而不进行混合、调整不透明度或应用任何剪切。
- 将滤镜应用到包含光栅化图像的图层。
- 使用上下文的当前混合模式、不透明度设置和剪辑形状，将图层合成到背景上。

当 SwiftUI 使用滤镜绘制时，混合模式可能会应用到绘制操作固有形状之外但在剪辑形状之内的区域。这可能会导致某些混合模式（如 [copy](BlendMode-swift_struct/copy.zh-Hans.md)）出现意外行为，即使源 alpha 为零，绘制操作也会完全覆盖背景。

## 过滤

- **GraphicsContext.Filter**：对渲染内容进行图像处理操作的类型。
- **GraphicsContext.FilterOptions**：用于配置添加到图形上下文的过滤器的选项。
- **GraphicsContext.BlurOptions**：用于配置创建模糊的图形上下文过滤器的选项。
- **GraphicsContext.ShadowOptions**：配置创建阴影的图形上下文过滤器的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/addFilter(_:options:)
crawled: 2025-12-02T20:58:22Z
---

# addFilter(_:options:)

**Instance Method**

Adds a filter that applies to subsequent drawing operations.

## Declaration

```swift
mutating func addFilter(_ filter: GraphicsContext.Filter, options: GraphicsContext.FilterOptions = FilterOptions())
```

## Parameters

- **filter**: A graphics context filter that you create by calling one of the [Filter](Filter.zh-Hans.md) factory methods.
- **options**: A set of options from [FilterOptions](FilterOptions.zh-Hans.md) that you can use to configure filter operations.

## Discussion

To draw with filtering, SwiftUI:

- Rasterizes the drawing operation to an implicit transparency layer without blending, adjusting opacity, or applying any clipping.
- Applies the filter to the layer containing the rasterized image.
- Composites the layer onto the background, using the context’s current blend mode, opacity setting, and clip shapes.

When SwiftUI draws with a filter, the blend mode might apply to regions outside the drawing operation’s intrinsic shape, but inside its clip shape. That might result in unexpected behavior for certain blend modes like [copy](BlendMode-swift_struct/copy.zh-Hans.md), where the drawing operation completely overwrites the background even if the source alpha is zero.

## Filtering

- **GraphicsContext.Filter**: A type that applies image processing operations to rendered content.
- **GraphicsContext.FilterOptions**: Options that configure a filter that you add to a graphics context.
- **GraphicsContext.BlurOptions**: Options that configure the graphics context filter that creates blur.
- **GraphicsContext.ShadowOptions**: Options that configure the graphics context filter that creates shadows.

