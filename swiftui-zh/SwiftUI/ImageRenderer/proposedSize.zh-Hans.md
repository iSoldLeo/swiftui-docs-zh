---
来源：https://developer.apple.com/documentation/SwiftUI/ImageRenderer/proposedSize
抓取时间： 2025-12-03T06:21:43Z
---

# 拟议大小

**实例属性**

建议的根视图大小。

## 声明

```swift
@MainActor final var proposedSize: ProposedViewSize { get set }
```

## 讨论

该属性的默认值[unspecified](../ProposedViewSize/unspecified.zh-Hans.md) 会生成与原始视图大小一致的图像。您可以自定义[ProposedViewSize](../ProposedViewSize.zh-Hans.md)，以覆盖视图在一个或两个维度上的尺寸。

## 访问呈现器属性

- **scale**：渲染图像的比例。
- **isOpaque**：布尔值，表示图像的 alpha 通道是否完全不透明。
- **colorMode**：图像的工作色彩空间和存储格式。
- **allowedDynamicRange**：图像的工作色彩空间和存储格式：图像允许的动态范围，或用 nil 表示图像的动态范围不受限制。此属性默认为 `sdr`，即 HDR 内容将被色调映射为 SDR。


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer/proposedSize
crawled: 2025-12-03T06:21:43Z
---

# proposedSize

**Instance Property**

The size proposed to the root view.

## Declaration

```swift
@MainActor final var proposedSize: ProposedViewSize { get set }
```

## Discussion

The default value of this property, [unspecified](../ProposedViewSize/unspecified.zh-Hans.md), produces an image that matches the original view size. You can provide a custom [ProposedViewSize](../ProposedViewSize.zh-Hans.md) to override the view’s size in one or both dimensions.

## Accessing renderer properties

- **scale**: The scale at which to render the image.
- **isOpaque**: A Boolean value that indicates whether the alpha channel of the image is fully opaque.
- **colorMode**: The working color space and storage format of the image.
- **allowedDynamicRange**: The allowed dynamic range of the image, or nil to mark that the dynamic range of the image should be unrestricted. This property defaults to `sdr`, i.e. HDR content will be tone mapped to SDR.

