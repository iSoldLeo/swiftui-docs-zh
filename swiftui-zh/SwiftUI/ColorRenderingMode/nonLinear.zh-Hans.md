--- 来源：https://developer.apple.com/documentation/SwiftUI/ColorRenderingMode/nonLinear

抓取时间：2025-12-03T06:32:17Z

---

# ColorRenderingMode.nonLinear

**Case**

非线性 sRGB 工作色彩空间。

## 声明

```swift
case nonLinear
```

## 讨论

超出 `[0, 1]` 范围的颜色分量值会产生未定义的结果。此色彩空间已进行伽马校正。

## 获取渲染模式

- **ColorRenderingMode.extendedLinear**：扩展线性 sRGB 工作色彩空间。

- **ColorRenderingMode.linear**：线性 sRGB 工作色彩空间。


---
source: https://developer.apple.com/documentation/SwiftUI/ColorRenderingMode/nonLinear
crawled: 2025-12-03T06:32:17Z
---

# ColorRenderingMode.nonLinear

**Case**

The non-linear sRGB working color space.

## Declaration

```swift
case nonLinear
```

## Discussion

Color component values outside the range `[0, 1]` produce undefined results. This color space is gamma corrected.

## Getting rendering modes

- **ColorRenderingMode.extendedLinear**: The extended linear sRGB working color space.
- **ColorRenderingMode.linear**: The linear sRGB working color space.

