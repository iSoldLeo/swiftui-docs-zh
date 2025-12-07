---
来源： https://developer.apple.com/documentation/SwiftUI/Image/antialiased(_:)
抓取时间： 2025-12-03T04:29:02Z
---

# antialiased(_:)

**实例方法**

指定 SwiftUI 在渲染图像时是否应用抗锯齿。

## 声明

```swift
func antialiased(_ isAntialiased: Bool) -> Image
```

## 参数

- **isAntialiased**：布尔值，用于指定是否允许抗锯齿。传递 `true` 表示允许反锯齿，否则传递 `false`。

## 返回值

已设置抗锯齿行为的图像。

## 指定渲染行为

- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。
- **renderingMode(_:)**：表示 SwiftUI 是按原样还是使用其他模式渲染图像。
- **interpolation(_:)**：指定渲染需要插值的图像时的当前质量级别。
- **Image.TemplateRenderingMode**：表示 SwiftUI 如何渲染图像的类型。
- **Image.Interpolation**：用于渲染需要插值的图像（如缩放图像）的质量级别。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/antialiased(_:)
crawled: 2025-12-03T04:29:02Z
---

# antialiased(_:)

**Instance Method**

Specifies whether SwiftUI applies antialiasing when rendering the image.

## Declaration

```swift
func antialiased(_ isAntialiased: Bool) -> Image
```

## Parameters

- **isAntialiased**: A Boolean value that specifies whether to allow antialiasing. Pass `true` to allow antialising, `false` otherwise.

## Return Value

An image with the antialiasing behavior set.

## Specifying rendering behavior

- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **renderingMode(_:)**: Indicates whether SwiftUI renders an image as-is, or by using a different mode.
- **interpolation(_:)**: Specifies the current level of quality for rendering an image that requires interpolation.
- **Image.TemplateRenderingMode**: A type that indicates how SwiftUI renders images.
- **Image.Interpolation**: The level of quality for rendering an image that requires interpolation, such as a scaled image.

