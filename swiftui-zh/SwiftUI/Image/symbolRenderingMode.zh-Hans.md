---
来源： https://developer.apple.com/documentation/SwiftUI/Image/symbolRenderingMode(_:)
抓取时间： 2025-12-01T09:18:27Z
---

# symbolRenderingMode(_:)

**实例方法**

设置此视图中符号图像的渲染模式。

## 声明

```swift
func symbolRenderingMode(_ mode: SymbolRenderingMode?) -> Image
```

## 参数

- **mode**：要使用的符号渲染模式。

## 返回值

使用您提供的渲染模式的视图。

## 指定渲染行为

- **antialiased(_:)**：指定 SwiftUI 在渲染图像时是否应用抗锯齿。
- **renderingMode(_:)**：表示 SwiftUI 是按原样渲染图像，还是使用不同的模式渲染图像。
- **interpolation(_:)**：指定渲染需要插值的图像时的当前质量级别。
- **Image.TemplateRenderingMode**：表示 SwiftUI 如何渲染图像的类型。
- **Image.Interpolation**：用于渲染需要插值的图像（如缩放图像）的质量级别。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/symbolRenderingMode(_:)
crawled: 2025-12-01T09:18:27Z
---

# symbolRenderingMode(_:)

**Instance Method**

Sets the rendering mode for symbol images within this view.

## Declaration

```swift
func symbolRenderingMode(_ mode: SymbolRenderingMode?) -> Image
```

## Parameters

- **mode**: The symbol rendering mode to use.

## Return Value

A view that uses the rendering mode you supply.

## Specifying rendering behavior

- **antialiased(_:)**: Specifies whether SwiftUI applies antialiasing when rendering the image.
- **renderingMode(_:)**: Indicates whether SwiftUI renders an image as-is, or by using a different mode.
- **interpolation(_:)**: Specifies the current level of quality for rendering an image that requires interpolation.
- **Image.TemplateRenderingMode**: A type that indicates how SwiftUI renders images.
- **Image.Interpolation**: The level of quality for rendering an image that requires interpolation, such as a scaled image.

