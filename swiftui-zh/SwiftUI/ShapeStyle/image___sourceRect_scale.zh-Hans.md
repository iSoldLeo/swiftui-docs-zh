--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/image(_:sourceRect:scale:)

抓取时间：2025-12-03T06:25:09Z

---

# image(_:sourceRect:scale:)

**类型方法**

一种形状样式，通过重复图像区域来填充形状。

## 声明

```swift
static func image(_ image: Image, sourceRect: CGRect = CGRect(x: 0, y: 0, width: 1, height: 1), scale: CGFloat = 1) -> ImagePaint
```

## 参数

- **image**：要绘制的图像。

- **sourceRect**：一个单位空间矩形，用于定义要绘制的源图像区域的大小。如果 `sourceRect` 选择的区域超出 `[0, 1]` 的范围（无论在哪个轴上），则结果未定义。

- **scale**：渲染过程中应用于图像的缩放因子。

## 讨论

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/image(_:sourceRect:scale:)
crawled: 2025-12-03T06:25:09Z
---

# image(_:sourceRect:scale:)

**Type Method**

A shape style that fills a shape by repeating a region of an image.

## Declaration

```swift
static func image(_ image: Image, sourceRect: CGRect = CGRect(x: 0, y: 0, width: 1, height: 1), scale: CGFloat = 1) -> ImagePaint
```

## Parameters

- **image**: The image to be drawn.
- **sourceRect**: A unit-space rectangle defining how much of the source image to draw. The results are undefined if `sourceRect` selects areas outside the `[0, 1]` range in either axis.
- **scale**: A scale factor applied to the image during rendering.

## Discussion

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

