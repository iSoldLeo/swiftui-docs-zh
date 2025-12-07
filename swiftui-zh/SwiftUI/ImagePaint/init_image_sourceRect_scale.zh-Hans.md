---
来源：https://developer.apple.com/documentation/SwiftUI/ImagePaint/init(image:sourceRect:scale:)
抓取时间：2025-12-02T05:19:16Z
---

# init(image:sourceRect:scale:)

**Initializer**

创建填充形状样式。

## 声明

```swift
init(image: Image, sourceRect: CGRect = CGRect(x: 0, y: 0, width: 1, height: 1), scale: CGFloat = 1)
```

## 参数

- **image**：要绘制的图像。
- **sourceRect**：单位空间矩形，定义要绘制的源图像的大小。如果`sourceRect` 在任一轴上选择了超出`[0, 1]` 范围的区域，结果将是未定义的。
- **scale**：渲染时应用于图像的比例因子。


---
source: https://developer.apple.com/documentation/SwiftUI/ImagePaint/init(image:sourceRect:scale:)
crawled: 2025-12-02T05:19:16Z
---

# init(image:sourceRect:scale:)

**Initializer**

Creates a shape-filling shape style.

## Declaration

```swift
init(image: Image, sourceRect: CGRect = CGRect(x: 0, y: 0, width: 1, height: 1), scale: CGFloat = 1)
```

## Parameters

- **image**: The image to be drawn.
- **sourceRect**: A unit-space rectangle defining how much of the source image to draw. The results are undefined if `sourceRect` selects areas outside the `[0, 1]` range in either axis.
- **scale**: A scale factor applied to the image during rendering.

