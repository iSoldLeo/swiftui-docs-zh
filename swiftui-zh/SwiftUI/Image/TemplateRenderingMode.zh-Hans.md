---
来源： https://developer.apple.com/documentation/SwiftUI/Image/TemplateRenderingMode
抓取时间： 2025-12-03T04:29:05Z
---

# Image.TemplateRenderingMode

**Enumeration**

表示 SwiftUI 如何渲染图像的类型。

## 声明

```swift
enum TemplateRenderingMode
```

## 获取渲染模式

- **Image.TemplateRenderingMode.original**：按原样渲染位图图像像素的模式。
- **Image.TemplateRenderingMode.template**：将所有非透明像素渲染为前景色的模式。

## 指定渲染行为

- **antialiased(_:)**：指定 SwiftUI 在渲染图像时是否应用抗锯齿。
- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。
- **renderingMode(_:)**：表示 SwiftUI 是按原样还是使用其他模式渲染图像。
- **interpolation(_:)**：指定渲染需要插值的图像时的当前质量级别。
- **Image.Interpolation**：渲染需要插值的图像（如缩放图像）的质量级别。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Image/TemplateRenderingMode
crawled: 2025-12-03T04:29:05Z
---

# Image.TemplateRenderingMode

**Enumeration**

A type that indicates how SwiftUI renders images.

## Declaration

```swift
enum TemplateRenderingMode
```

## Getting rendering modes

- **Image.TemplateRenderingMode.original**: A mode that renders pixels of bitmap images as-is.
- **Image.TemplateRenderingMode.template**: A mode that renders all non-transparent pixels as the foreground color.

## Specifying rendering behavior

- **antialiased(_:)**: Specifies whether SwiftUI applies antialiasing when rendering the image.
- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **renderingMode(_:)**: Indicates whether SwiftUI renders an image as-is, or by using a different mode.
- **interpolation(_:)**: Specifies the current level of quality for rendering an image that requires interpolation.
- **Image.Interpolation**: The level of quality for rendering an image that requires interpolation, such as a scaled image.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

