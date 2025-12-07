---
来源： https://developer.apple.com/documentation/SwiftUI/ImageRenderer/scale
抓取时间： 2025-12-03T06:21:43Z
---

# 比例

**实例属性**

渲染图像的比例。

## 声明

```swift
@MainActor final var scale: CGFloat { get set }
```

## 讨论

该值是视点与图像像素的比率。这种关系意味着，大于 `1.0` 的值创建的图像比原始内容视图大，小于 `1.0` 的值创建的图像较小。下面的示例显示了一个 100 x 50 的矩形视图和从中渲染出的`scale`为`2.0`的图像，结果图像大小为 200 x 100。

```swift
let rectangle = Rectangle()
    .frame(width: 100, height: 50)
let renderer = ImageRenderer(content: rectangle)
renderer.scale = 2.0
if let rendered = renderer.cgImage {
    print("Scaled image: \(rendered.width) x \(rendered.height)")
}
// Prints "Scaled image: 200 x 100"
```

此属性的默认值为 `1.0`。

## 访问呈现器属性

- **proposedSize**：建议的根视图大小。
- **isOpaque**：布尔值，表示图像的 alpha 通道是否完全不透明。
- **colorMode**：图像的工作色彩空间和存储格式。
- **allowedDynamicRange**：图像允许的动态范围，或用 nil 表示图像的动态范围不受限制。此属性默认为 `sdr`，即 HDR 内容将被色调映射为 SDR。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/scale
crawled: 2025-12-03T06:21:43Z
---

# scale

**Instance Property**

The scale at which to render the image.

## Declaration

```swift
@MainActor final var scale: CGFloat { get set }
```

## Discussion

This value is a ratio of view points to image pixels. This relationship means that values greater than `1.0` create an image larger than the original content view, and less than `1.0` creates a smaller image. The following example shows a 100 x 50 rectangle view and an image rendered from it with a `scale` of `2.0`, resulting in an image size of 200 x 100.

```swift
let rectangle = Rectangle()
    .frame(width: 100, height: 50)
let renderer = ImageRenderer(content: rectangle)
renderer.scale = 2.0
if let rendered = renderer.cgImage {
    print("Scaled image: \(rendered.width) x \(rendered.height)")
}
// Prints "Scaled image: 200 x 100"
```

The default value of this property is `1.0`.

## Accessing renderer properties

- **proposedSize**: The size proposed to the root view.
- **isOpaque**: A Boolean value that indicates whether the alpha channel of the image is fully opaque.
- **colorMode**: The working color space and storage format of the image.
- **allowedDynamicRange**: The allowed dynamic range of the image, or nil to mark that the dynamic range of the image should be unrestricted. This property defaults to `sdr`, i.e. HDR content will be tone mapped to SDR.

