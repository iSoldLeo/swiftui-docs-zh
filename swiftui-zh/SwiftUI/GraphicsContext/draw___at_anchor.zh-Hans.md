---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)
抓取时间：2025-12-02T20:58:09Z
---

# draw(_:at:anchor:)

**实例方法**

在上下文中绘制已解析的图像，将图像中的锚点与上下文中的点对齐。

## 声明

```swift
func draw(_ image: GraphicsContext.ResolvedImage, at point: CGPoint, anchor: UnitPoint = .center)
```

## 参数

- **image**：要绘制的[ResolvedImage](ResolvedImage.zh-Hans.md)。通过调用[doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-898z6]，从[Image](../Image.zh-Hans.md)中获取解析图像。或者，也可以使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-7l217] 调用 [Image](../Image.zh-Hans.md)，该方法会自动执行解析。
- **point**：解析图像矩形内的一点，用于锚定上下文中的一点。
- **anchor**：上下文中要对齐图像的[UnitPoint](../UnitPoint.zh-Hans.md)。默认值为 [center](../UnitPoint/center.zh-Hans.md)。

### 讨论

当前上下文状态定义了完整的绘图操作。例如，当前的变换和剪切形状会影响 SwiftUI 绘制图像的方式。

## 绘制图像、文本和视图

- **draw(_:in:)**：使用指定的矩形作为布局框架，在上下文中绘制已解析的符号。
- **draw(_:in:style:)**：使用指定的矩形作为布局框架，在上下文中绘制解析图像。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)
crawled: 2025-12-02T20:58:09Z
---

# draw(_:at:anchor:)

**Instance Method**

Draws a resolved image into the context, aligning an anchor within the image to a point in the context.

## Declaration

```swift
func draw(_ image: GraphicsContext.ResolvedImage, at point: CGPoint, anchor: UnitPoint = .center)
```

## Parameters

- **image**: The [ResolvedImage](ResolvedImage.zh-Hans.md) to draw. Get a resolved image from an [Image](../Image.zh-Hans.md) by calling [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-898z6]. Alternatively, you can call [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-7l217] with an [Image](../Image.zh-Hans.md), and that method performs the resolution automatically.
- **point**: A point within the rectangle of the resolved image to anchor to a point in the context.
- **anchor**: A [UnitPoint](../UnitPoint.zh-Hans.md) within the context to align the image with. The default is [center](../UnitPoint/center.zh-Hans.md).

## Discussion

The current context state defines the full drawing operation. For example, the current transformation and clip shapes affect how SwiftUI draws the image.

## Drawing images, text, and views

- **draw(_:in:)**: Draws a resolved symbol into the context, using the specified rectangle as a layout frame.
- **draw(_:in:style:)**: Draws a resolved image into the context, using the specified rectangle as a layout frame.

