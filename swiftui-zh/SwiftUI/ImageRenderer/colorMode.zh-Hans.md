---
来源： https://developer.apple.com/documentation/SwiftUI/ImageRenderer/colorMode
抓取时间： 2025-12-03T06:21:45Z
---

# colorMode

**实例属性**

图像的工作色彩空间和存储格式。

## 声明

```swift
@MainActor final var colorMode: ColorRenderingMode { get set }
```

## 访问呈现器属性

- **proposedSize**：建议的根视图大小。
- **scale**：渲染图像的比例。
- **isOpaque**：布尔值，表示图像的 alpha 通道是否完全不透明。
- **allowedDynamicRange**：图像允许的动态范围，或者用 nil 表示图像的动态范围不受限制。此属性默认为 `sdr`，即 HDR 内容将被色调映射为 SDR。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/colorMode
crawled: 2025-12-03T06:21:45Z
---

# colorMode

**Instance Property**

The working color space and storage format of the image.

## Declaration

```swift
@MainActor final var colorMode: ColorRenderingMode { get set }
```

## Accessing renderer properties

- **proposedSize**: The size proposed to the root view.
- **scale**: The scale at which to render the image.
- **isOpaque**: A Boolean value that indicates whether the alpha channel of the image is fully opaque.
- **allowedDynamicRange**: The allowed dynamic range of the image, or nil to mark that the dynamic range of the image should be unrestricted. This property defaults to `sdr`, i.e. HDR content will be tone mapped to SDR.

