---
来源： https://developer.apple.com/documentation/SwiftUI/Image/ResizingMode
抓取时间： 2025-12-02T17:35:49Z
---

# Image.ResizingMode

**Enumeration**

SwiftUI 用来调整图像大小以适应其包含的视图的模式。

## 声明

```swift
enum ResizingMode
```

## 获取大小调整模式

- **Image.ResizingMode.stretch**：放大或缩小图像的模式，使其填满可用空间。
- **Image.ResizingMode.tile**：以原始大小重复显示图像的模式，可根据需要多次重复显示以填充可用空间。

## 配置图像

- 将图像放入可用空间**：通过应用视图修改器，调整应用程序用户界面中图像的大小和形状。
- **imageScale(_:)**：根据可用的相对尺寸（包括小、中和大图片尺寸）之一来缩放视图中的图片。
- **imageScale**：此环境的图像比例。
- **Image.Scale**：相对于文本应用于矢量图像的比例。
- **Image.Orientation**：图像的方向。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Image/ResizingMode
crawled: 2025-12-02T17:35:49Z
---

# Image.ResizingMode

**Enumeration**

The modes that SwiftUI uses to resize an image to fit within its containing view.

## Declaration

```swift
enum ResizingMode
```

## Getting resizing modes

- **Image.ResizingMode.stretch**: A mode to enlarge or reduce the size of an image so that it fills the available space.
- **Image.ResizingMode.tile**: A mode to repeat the image at its original size, as many times as necessary to fill the available space.

## Configuring an image

- **Fitting images into available space**: Adjust the size and shape of images in your app’s user interface by applying view modifiers.
- **imageScale(_:)**: Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.
- **imageScale**: The image scale for this environment.
- **Image.Scale**: A scale to apply to vector images relative to text.
- **Image.Orientation**: The orientation of an image.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

