---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)
抓取时间：2025-12-02T20:58:08Z
---

# draw(_:in:style:)

**实例方法**

使用指定的矩形作为布局框架，在上下文中绘制已解析的图像。

## 声明

```swift
func draw(_ image: GraphicsContext.ResolvedImage, in rect: CGRect, style: FillStyle = FillStyle())
```

## 参数

- **image**：要绘制的[ResolvedImage](ResolvedImage.zh-Hans.md)。通过调用 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-898z6]，从[Image](../Image.zh-Hans.md)中获取解析图像。或者，也可以用 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)-blhz] 调用 [Image](../Image.zh-Hans.md)，该方法会自动执行解析。
- **rect**：当前用户空间中绘制图像的矩形。
- **style**：光栅化图像时使用的填充样式。

## 讨论

当前的上下文状态定义了完整的绘制操作。例如，当前的变换和剪切形状会影响 SwiftUI 绘制图像的方式。

## 绘制图像、文本和视图

- **draw(_:in:)**：使用指定的矩形作为布局框架，在上下文中绘制已解析的符号。
- **draw(_:at:anchor:)**：在上下文中绘制解析图像，将图像中的锚点与上下文中的点对齐。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)
crawled: 2025-12-02T20:58:08Z
---

# draw(_:in:style:)

**Instance Method**

Draws a resolved image into the context, using the specified rectangle as a layout frame.

## Declaration

```swift
func draw(_ image: GraphicsContext.ResolvedImage, in rect: CGRect, style: FillStyle = FillStyle())
```

## Parameters

- **image**: The [ResolvedImage](ResolvedImage.zh-Hans.md) to draw. Get a resolved image from an [Image](../Image.zh-Hans.md) by calling [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-898z6]. Alternatively, you can call [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)-blhz] with an [Image](../Image.zh-Hans.md), and that method performs the resolution automatically.
- **rect**: The rectangle in the current user space to draw the image in.
- **style**: A fill style to use when rasterizing the image.

## Discussion

The current context state defines the full drawing operation. For example, the current transformation and clip shapes affect how SwiftUI draws the image.

## Drawing images, text, and views

- **draw(_:in:)**: Draws a resolved symbol into the context, using the specified rectangle as a layout frame.
- **draw(_:at:anchor:)**: Draws a resolved image into the context, aligning an anchor within the image to a point in the context.

