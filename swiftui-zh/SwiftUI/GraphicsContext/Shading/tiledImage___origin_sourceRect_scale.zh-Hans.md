---
来源: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/tiledImage(_:origin:sourceRect:scale:)
抓取时间：2025-12-01T22:05:08Z
---

# tiledImage(_:origin:sourceRect:scale:)

**类型方法**

返回在无限平面上平铺图像的着色实例。

## 声明

```swift
static func tiledImage(_ image: Image, origin: CGPoint = .zero, sourceRect: CGRect = CGRect(x: 0, y: 0, width: 1, height: 1), scale: CGFloat = 1) -> GraphicsContext.Shading
```

## 参数

- **image**：用于填充的[Image](../../Image.zh-Hans.md)。
- **origin**：当前用户空间中 SwiftUI 放置`sourceRect` 所定义图像部分左下角的位置。图像会根据需要重复显示。
- **sourceRect**：图像的单位空间子区域。默认为单位矩形，选择整个图像。
- **scale**：用于控制图像大小的系数。

## 返回值

填充了平铺图像的着色实例。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/tiledImage(_:origin:sourceRect:scale:)
crawled: 2025-12-01T22:05:08Z
---

# tiledImage(_:origin:sourceRect:scale:)

**Type Method**

Returns a shading instance that tiles an image across the infinite plane.

## Declaration

```swift
static func tiledImage(_ image: Image, origin: CGPoint = .zero, sourceRect: CGRect = CGRect(x: 0, y: 0, width: 1, height: 1), scale: CGFloat = 1) -> GraphicsContext.Shading
```

## Parameters

- **image**: An [Image](../../Image.zh-Hans.md) to use as fill.
- **origin**: The point in the current user space where SwiftUI places the bottom left corner of the part of the image defined by `sourceRect`. The image repeats as needed.
- **sourceRect**: A unit space subregion of the image. The default is a unit rectangle, which selects the whole image.
- **scale**: A factor that you can use to control the image size.

## Return Value

A shading instance filled with a tiled image.

