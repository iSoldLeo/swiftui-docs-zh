---
来源：https://developer.apple.com/documentation/SwiftUI/Canvas/init(opaque:colorMode:rendersAsynchronously:renderer:)
抓取时间：2025-12-02T20:57:59Z
---

# init(opaque:colorMode:rendersAsynchronously:renderer:)

**Initializer**

创建并配置画布。

## 声明

```swift
init(opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear, rendersAsynchronously: Bool = false, renderer: @escaping (inout GraphicsContext, CGSize) -> Void)
```

## 参数

- **opaque**：布尔值，表示画布是否完全不透明。将该值设置为 `true`可能会提高性能，但在上下文中绘制非不透明图像会产生未定义的结果。默认值为`false`。
- **colorMode**：画布的工作色彩空间和存储格式。默认为[nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md)。
- **rendersAsynchronously**：布尔值，表示画布是否可以异步向父视图显示其内容。默认值为 `false`。
- **renderer**：用于立即模式绘图的闭包。该闭包接收两个输入：一个用于发出绘制命令的上下文，以及一个代表画布当前大小的尺寸，用于自定义内容。画布在需要重绘内容时会调用呈现器。

## 讨论

使用此初始化程序可创建一个新画布，并在其中绘图。例如，您可以绘制一条路径：

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

上面的示例绘制了一个椭圆的轮廓，该椭圆正好嵌入一个带有蓝色边框的画布中：



有关使用上下文绘制画布的信息，请参阅[GraphicsContext](../GraphicsContext.zh-Hans.md)。如果要提供 SwiftUI 视图供呈现器用作绘制元素，请使用 [init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)](init_opaque_colorMode_rendersAsynchronously_renderer_symbols.zh-Hans.md) 代替。

## 创建画布

- **init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)**：创建并配置画布，并为其提供可渲染的子视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Canvas/init(opaque:colorMode:rendersAsynchronously:renderer:)
crawled: 2025-12-02T20:57:59Z
---

# init(opaque:colorMode:rendersAsynchronously:renderer:)

**Initializer**

Creates and configures a canvas.

## Declaration

```swift
init(opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear, rendersAsynchronously: Bool = false, renderer: @escaping (inout GraphicsContext, CGSize) -> Void)
```

## Parameters

- **opaque**: A Boolean that indicates whether the canvas is fully opaque. You might be able to improve performance by setting this value to `true`, but then drawing a non-opaque image into the context produces undefined results. The default is `false`.
- **colorMode**: A working color space and storage format of the canvas. The default is [nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md).
- **rendersAsynchronously**: A Boolean that indicates whether the canvas can present its contents to its parent view asynchronously. The default is `false`.
- **renderer**: A closure in which you conduct immediate mode drawing. The closure takes two inputs: a context that you use to issue drawing commands and a size — representing the current size of the canvas — that you can use to customize the content. The canvas calls the renderer any time it needs to redraw the content.

## Discussion

Use this initializer to create a new canvas that you can draw into. For example, you can draw a path:

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



For information about using a context to draw into a canvas, see [GraphicsContext](../GraphicsContext.zh-Hans.md). If you want to provide SwiftUI views for the renderer to use as drawing elements, use [init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)](init_opaque_colorMode_rendersAsynchronously_renderer_symbols.zh-Hans.md) instead.

## Creating a canvas

- **init(opaque:colorMode:rendersAsynchronously:renderer:symbols:)**: Creates and configures a canvas that you supply with renderable child views.

