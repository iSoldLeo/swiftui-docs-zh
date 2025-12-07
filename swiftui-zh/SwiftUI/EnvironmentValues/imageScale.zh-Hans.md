---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/imageScale
抓取时间： 2025-12-02T17:35:47Z
---

# imageScale

**实例属性**

此环境的图像比例。

## 声明

```swift
var imageScale: Image.Scale { get set }
```

## 配置图像

- 将图像调整到可用空间**：通过应用视图修改器调整应用程序用户界面中图像的大小和形状。
- **imageScale(_:)**：根据可用的相对尺寸（包括小、中和大图片尺寸）之一来缩放视图中的图片。
- **Image.Scale**：相对于文本应用于矢量图像的比例。
- **Image.Orientation**：图像的方向。
- **Image.ResizingMode**：SwiftUI 用来调整图像大小以适合其包含的视图的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/imageScale
crawled: 2025-12-02T17:35:47Z
---

# imageScale

**Instance Property**

The image scale for this environment.

## Declaration

```swift
var imageScale: Image.Scale { get set }
```

## Configuring an image

- **Fitting images into available space**: Adjust the size and shape of images in your app’s user interface by applying view modifiers.
- **imageScale(_:)**: Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.
- **Image.Scale**: A scale to apply to vector images relative to text.
- **Image.Orientation**: The orientation of an image.
- **Image.ResizingMode**: The modes that SwiftUI uses to resize an image to fit within its containing view.

