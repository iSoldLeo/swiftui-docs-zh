---
来源： https://developer.apple.com/documentation/SwiftUI/Image/Orientation
抓取时间： 2025-12-02T17:35:49Z
---

# 图像方向

**Enumeration**

图像的方向。

## 声明

```swift
@frozen enum Orientation
```

## 概览

许多图像格式（如 JPEG）都在图像数据中包含方向元数据。在其他情况下，您可以在代码中指定图像方向。正确指定方向通常对显示图像和某些图像处理都很重要。

在 SwiftUI 中，您可以在从现有[Image](../Image.zh-Hans.md) 初始化[doc://com.apple.documentation/documentation/CoreGraphics/CGImage] 时提供方向值。

## 获取图像方向

- **Image.Orientation.up**：表示原始像素数据与图像预期显示方向相匹配的值。
- **Image.Orientation.down**：表示图像从其原始像素数据方向旋转 180° 的值。
- **Image.Orientation.left**：表示从原始像素数据的方向逆时针旋转 90° 的值。
- **Image.Orientation.right**：表示图像从其原始像素数据的方向顺时针旋转 90° 的值。

## 获取镜像图像的方向

- **Image.Orientation.upMirrored**：表示图像从其原始像素数据方向水平翻转的值。
- **Image.Orientation.downMirrored**：表示图像从原始像素数据方向垂直翻转的值。
- **Image.Orientation.leftMirrored**：表示图像从其原始像素数据的方向顺时针旋转 90° 并水平翻转的值。
- **Image.Orientation.rightMirrored**：表示逆时针旋转 90° 并从原始像素数据的方向水平翻转的值。

## 配置图像

- 使图像适合可用空间**：通过应用视图修改器，调整应用程序用户界面中图像的大小和形状。
- **imageScale(_:)**：根据可用的相对尺寸（包括小、中和大图片尺寸）之一缩放视图中的图片。
- **imageScale**：此环境的图像比例。
- **Image.Scale**：相对于文本应用于矢量图像的比例。
- **Image.ResizingMode**：SwiftUI 用于调整图像大小以适应其包含的视图的模式。

## 符合

- 比特可复制
- CaseIterable
- 可复制
- 等价
- Hashable
- 原始可表示
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Image/Orientation
crawled: 2025-12-02T17:35:49Z
---

# Image.Orientation

**Enumeration**

The orientation of an image.

## Declaration

```swift
@frozen enum Orientation
```

## Overview

Many image formats such as JPEG include orientation metadata in the image data. In other cases, you can specify image orientation in code. Properly specifying orientation is often important both for displaying the image and for certain kinds of image processing.

In SwiftUI, you provide an orientation value when initializing an [Image](../Image.zh-Hans.md) from an existing [doc://com.apple.documentation/documentation/CoreGraphics/CGImage].

## Getting image orientations

- **Image.Orientation.up**: A value that indicates the original pixel data matches the image’s intended display orientation.
- **Image.Orientation.down**: A value that indicates a 180° rotation of the image from the orientation of its original pixel data.
- **Image.Orientation.left**: A value that indicates a 90° counterclockwise rotation from the orientation of its original pixel data.
- **Image.Orientation.right**: A value that indicates a 90° clockwise rotation of the image from the orientation of its original pixel data.

## Getting mirrored image orientation

- **Image.Orientation.upMirrored**: A value that indicates a horizontal flip of the image from the orientation of its original pixel data.
- **Image.Orientation.downMirrored**: A value that indicates a vertical flip of the image from the orientation of its original pixel data.
- **Image.Orientation.leftMirrored**: A value that indicates a 90° clockwise rotation and horizontal flip of the image from the orientation of its original pixel data.
- **Image.Orientation.rightMirrored**: A value that indicates a 90° counterclockwise rotation and horizontal flip from the orientation of its original pixel data.

## Configuring an image

- **Fitting images into available space**: Adjust the size and shape of images in your app’s user interface by applying view modifiers.
- **imageScale(_:)**: Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.
- **imageScale**: The image scale for this environment.
- **Image.Scale**: A scale to apply to vector images relative to text.
- **Image.ResizingMode**: The modes that SwiftUI uses to resize an image to fit within its containing view.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

