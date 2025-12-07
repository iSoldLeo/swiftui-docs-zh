---
来源： https://developer.apple.com/documentation/SwiftUI/Canvas
抓取时间： 2025-12-02T16:15:43Z
---

# 帆布

**Structure**

支持即时模式绘图的视图类型。

## 声明

```swift
struct Canvas<Symbols> where Symbols : View
```

## 概览

在 SwiftUI 视图中使用画布绘制丰富的动态 2D 图形。画布会将[GraphicsContext](GraphicsContext.zh-Hans.md) 传递给闭包，用于执行即时模式绘图操作。画布还会传递[doc://com.apple.documentation/documentation/CoreFoundation/CGSize] 值，您可以使用该值自定义绘制内容。例如，您可以使用上下文的[stroke(_:with:lineWidth:)](GraphicsContext/stroke___with_lineWidth.zh-Hans.md) 命令来绘制[Path](Path.zh-Hans.md) 实例：

```swift
Canvas { context, size in
    context.stroke(
        Path(ellipseIn: CGRect(origin: .zero, size: size)),
        with: .color(.green),
        lineWidth: 4)
}
.frame(width: 300, height: 200)
.border(Color.blue)
```

上面的示例绘制了一个椭圆的轮廓，该椭圆恰好刻画了带有蓝色边框的画布：



除了勾画和填充路径外，您还可以绘制图像、文本和完整的 SwiftUI 视图。要绘制视图，请使用[init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)](Canvas/init_opaque_colorMode_rendersAsynchronously_renderer_symbols.zh-Hans.md) 方法提供视图，以便从呈现器内部引用。您还可以添加遮罩、应用滤镜、执行变换、控制混合等。有关如何绘制的信息，请参阅[GraphicsContext](GraphicsContext.zh-Hans.md)。

画布无法为单个元素（包括作为符号传入的视图）提供交互性或可访问性。不过，对于涉及动态数据的复杂绘图，画布可能会提供更好的性能。对于主要不涉及文本或不需要交互式元素的绘图，使用画布可以提高性能。

## 创建画布

- **init(opaque:colorMode:rendersAsynchronously:renderer:)**：创建并配置画布。
- **init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)**：创建并配置画布，并为其提供可渲染的子视图。

## 管理不透明度和颜色

- **isOpaque**：布尔值，表示画布是否完全不透明。
- **colorMode**：画布的工作色彩空间和存储格式。

## 引用符号

- **symbols**：提供子视图的视图，可在绘图回调中使用。

## 渲染

- **rendersAsynchronously**：布尔值，表示画布是否可以异步将其内容呈现给父视图。
- **renderer**：用于绘制画布的绘制回调。

## 即时模式绘制

- 为您的 SwiftUI 应用程序添加丰富的图形**：通过添加背景材质、鲜艳度、自定义图形和动画，让您的应用程序脱颖而出。
- **GraphicsContext**：即时模式绘图目标及其当前状态。

## 符合

- 可复制
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/Canvas
crawled: 2025-12-02T16:15:43Z
---

# Canvas

**Structure**

A view type that supports immediate mode drawing.

## Declaration

```swift
struct Canvas<Symbols> where Symbols : View
```

## Overview

Use a canvas to draw rich and dynamic 2D graphics inside a SwiftUI view. The canvas passes a [GraphicsContext](GraphicsContext.zh-Hans.md) to the closure that you use to perform immediate mode drawing operations. The canvas also passes a [doc://com.apple.documentation/documentation/CoreFoundation/CGSize] value that you can use to customize what you draw. For example, you can use the context’s [stroke(_:with:lineWidth:)](GraphicsContext/stroke___with_lineWidth.zh-Hans.md) command to draw a [Path](Path.zh-Hans.md) instance:

```swift
Canvas { context, size in
    context.stroke(
        Path(ellipseIn: CGRect(origin: .zero, size: size)),
        with: .color(.green),
        lineWidth: 4)
}
.frame(width: 300, height: 200)
.border(Color.blue)
```

The example above draws the outline of an ellipse that exactly inscribes a canvas with a blue border:



In addition to outlined and filled paths, you can draw images, text, and complete SwiftUI views. To draw views, use the [init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)](Canvas/init_opaque_colorMode_rendersAsynchronously_renderer_symbols.zh-Hans.md) method to supply views that you can reference from inside the renderer. You can also add masks, apply filters, perform transforms, control blending, and more. For information about how to draw, see [GraphicsContext](GraphicsContext.zh-Hans.md).

A canvas doesn’t offer interactivity or accessibility for individual elements, including for views that you pass in as symbols. However, it might provide better performance for a complex drawing that involves dynamic data. Use a canvas to improve performance for a drawing that doesn’t primarily involve text or require interactive elements.

## Creating a canvas

- **init(opaque:colorMode:rendersAsynchronously:renderer:)**: Creates and configures a canvas.
- **init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)**: Creates and configures a canvas that you supply with renderable child views.

## Managing opacity and color

- **isOpaque**: A Boolean that indicates whether the canvas is fully opaque.
- **colorMode**: The working color space and storage format of the canvas.

## Referencing symbols

- **symbols**: A view that provides child views that you can use in the drawing callback.

## Rendering

- **rendersAsynchronously**: A Boolean that indicates whether the canvas can present its contents to its parent view asynchronously.
- **renderer**: The drawing callback that you use to draw into the canvas.

## Immediate mode drawing

- **Add rich graphics to your SwiftUI app**: Make your apps stand out by adding background materials, vibrancy, custom graphics, and animations.
- **GraphicsContext**: An immediate mode drawing destination, and its current state.

## Conforms To

- Copyable
- View

