---
来源： https://developer.apple.com/documentation/SwiftUI/Image/Interpolation
抓取时间： 2025-12-03T04:29:06Z
---

# 图像插值

**Enumeration**

用于渲染需要插值的图像（如缩放图像）的质量级别。

## 声明

```swift
enum Interpolation
```

## 概览

[interpolation(_:)](interpolation.zh-Hans.md)修改器指定在[resizable(capInsets:resizingMode:)](resizable_capInsets_resizingMode.zh-Hans.md)修改器上使用[Image](../Image.zh-Hans.md)修改器时的插值行为。使用此行为可优先考虑渲染性能或图像质量。

## 获取插值选项

- **Image.Interpolation.high**：表示高水平插值质量的值，可能会降低图像渲染速度。
- **Image.Interpolation.low**：该值表示插值质量水平较低，可能会加快图像渲染速度。
- **Image.Interpolation.medium**：表示中等插值质量，介于低质量和高质量之间。
- **Image.Interpolation.none**：表示 SwiftUI 不对图像数据进行插值的值。

## 指定渲染行为

- **antialiased(_:)**：指定 SwiftUI 在渲染图像时是否应用抗锯齿。
- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。
- **renderingMode(_:)**：表示 SwiftUI 是按原样还是使用其他模式渲染图像。
- **interpolation(_:)**：指定渲染需要插值的图像时的当前质量级别。
- **Image.TemplateRenderingMode**：表示 SwiftUI 如何渲染图像的类型。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Image/Interpolation
crawled: 2025-12-03T04:29:06Z
---

# Image.Interpolation

**Enumeration**

The level of quality for rendering an image that requires interpolation, such as a scaled image.

## Declaration

```swift
enum Interpolation
```

## Overview

The [interpolation(_:)](interpolation.zh-Hans.md) modifier specifies the interpolation behavior when using the [resizable(capInsets:resizingMode:)](resizable_capInsets_resizingMode.zh-Hans.md) modifier on an [Image](../Image.zh-Hans.md). Use this behavior to prioritize rendering performance or image quality.

## Getting interpolation options

- **Image.Interpolation.high**: A value that indicates a high level of interpolation quality, which may slow down image rendering.
- **Image.Interpolation.low**: A value that indicates a low level of interpolation quality, which may speed up image rendering.
- **Image.Interpolation.medium**: A value that indicates a medium level of interpolation quality, between the low- and high-quality values.
- **Image.Interpolation.none**: A value that indicates SwiftUI doesn’t interpolate image data.

## Specifying rendering behavior

- **antialiased(_:)**: Specifies whether SwiftUI applies antialiasing when rendering the image.
- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **renderingMode(_:)**: Indicates whether SwiftUI renders an image as-is, or by using a different mode.
- **interpolation(_:)**: Specifies the current level of quality for rendering an image that requires interpolation.
- **Image.TemplateRenderingMode**: A type that indicates how SwiftUI renders images.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

