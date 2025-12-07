---
来源： https://developer.apple.com/documentation/SwiftUI/ImageRenderer/isOpaque
抓取时间： 2025-12-03T06:21:44Z
---

# isOpaque

**实例属性**

布尔值，表示图像的 alpha 通道是否完全不透明。

## 声明

```swift
@MainActor final var isOpaque: Bool { get set }
```

## 讨论

将此值设置为 `true`，表示 alpha 通道不透明，可以提高性能。不要向声明为不透明的呈现器呈现非不透明像素。此属性默认为 `false`。

## 访问呈现器属性

- **proposedSize**：建议的根视图大小。
- **scale**：渲染图像的比例。
- **colorMode**：图像的工作色彩空间和存储格式。
- **allowedDynamicRange**：图像允许的动态范围，或用 nil 表示图像的动态范围不受限制。此属性默认为 `sdr`，即 HDR 内容将被色调映射为 SDR。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/isOpaque
crawled: 2025-12-03T06:21:44Z
---

# isOpaque

**Instance Property**

A Boolean value that indicates whether the alpha channel of the image is fully opaque.

## Declaration

```swift
@MainActor final var isOpaque: Bool { get set }
```

## Discussion

Setting this value to `true`, meaning the alpha channel is opaque, may improve performance. Don’t render non-opaque pixels to a renderer declared as opaque. This property defaults to `false`.

## Accessing renderer properties

- **proposedSize**: The size proposed to the root view.
- **scale**: The scale at which to render the image.
- **colorMode**: The working color space and storage format of the image.
- **allowedDynamicRange**: The allowed dynamic range of the image, or nil to mark that the dynamic range of the image should be unrestricted. This property defaults to `sdr`, i.e. HDR content will be tone mapped to SDR.

