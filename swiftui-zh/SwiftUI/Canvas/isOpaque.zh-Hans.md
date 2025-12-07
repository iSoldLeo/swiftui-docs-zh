---
来源： https://developer.apple.com/documentation/SwiftUI/Canvas/isOpaque
抓取时间：2025-12-02T20:58:00Z
---

# isOpaque

**实例属性**

布尔值，表示画布是否完全不透明。

## 声明

```swift
var isOpaque: Bool { get set }
```

## 讨论

如果将此值设置为 `true`，使画布完全不透明，也许可以提高性能。但是，在这种情况下，在画布中绘制非不透明图像的结果是未定义的。

### 管理不透明度和颜色

- **colorMode**：画布的工作色彩空间和存储格式。


---
source: https://developer.apple.com/documentation/SwiftUI/Canvas/isOpaque
crawled: 2025-12-02T20:58:00Z
---

# isOpaque

**Instance Property**

A Boolean that indicates whether the canvas is fully opaque.

## Declaration

```swift
var isOpaque: Bool { get set }
```

## Discussion

You might be able to improve performance by setting this value to `true`, making the canvas is fully opaque. However, in that case, the result of drawing a non-opaque image into the canvas is undefined.

## Managing opacity and color

- **colorMode**: The working color space and storage format of the canvas.

