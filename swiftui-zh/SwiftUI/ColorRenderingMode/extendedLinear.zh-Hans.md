--- 来源：https://developer.apple.com/documentation/SwiftUI/ColorRenderingMode/extendedLinear

抓取时间：2025-12-03T06:32:16Z

---

# ColorRenderingMode.extendedLinear

**Case**

扩展线性 sRGB 工作色彩空间。

## 声明

```swift
case extendedLinear
```

## 讨论

`[0, 1]` 范围之外的颜色分量值将被保留。此色彩空间未进行伽马校正。

## 获取渲染模式

- **ColorRenderingMode.linear**：线性 sRGB 工作色彩空间。

- **ColorRenderingMode.nonLinear**：非线性 sRGB 工作色彩空间。


---
source: https://developer.apple.com/documentation/SwiftUI/ColorRenderingMode/extendedLinear
crawled: 2025-12-03T06:32:16Z
---

# ColorRenderingMode.extendedLinear

**Case**

The extended linear sRGB working color space.

## Declaration

```swift
case extendedLinear
```

## Discussion

Color component values outside the range `[0, 1]` are preserved. This color space isn’t gamma corrected.

## Getting rendering modes

- **ColorRenderingMode.linear**: The linear sRGB working color space.
- **ColorRenderingMode.nonLinear**: The non-linear sRGB working color space.

