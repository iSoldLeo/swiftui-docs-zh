---
来源： https://developer.apple.com/documentation/SwiftUI/ImagePaint/sourceRect
抓取时间： 2025-12-04T01:49:01Z
---

# sourceRect

**实例属性**

单位空间矩形，定义要绘制多少源图像。

## 声明

```swift
var sourceRect: CGRect
```

## 讨论

如果该矩形选择的区域超出`[0, 1]` 范围的任一轴，则结果未定义。

## 配置图像绘制样式

- **image**：要绘制的图像。
- **scale**：绘制时应用于图像的比例因子。


---
source: https://developer.apple.com/documentation/SwiftUI/ImagePaint/sourceRect
crawled: 2025-12-04T01:49:01Z
---

# sourceRect

**Instance Property**

A unit-space rectangle defining how much of the source image to draw.

## Declaration

```swift
var sourceRect: CGRect
```

## Discussion

The results are undefined if this rectangle selects areas outside the `[0, 1]` range in either axis.

## Configuring the image paint style

- **image**: The image to be drawn.
- **scale**: A scale factor applied to the image while being drawn.

