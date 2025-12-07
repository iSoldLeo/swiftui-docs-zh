--- 来源：https://developer.apple.com/documentation/SwiftUI/ColorRenderingMode/linear
抓取时间：2025-12-03T06:32:16Z

---

# ColorRenderingMode.linear

**Case**

线性 sRGB 工作色彩空间。

## 声明

```swift
case linear
```

## 讨论

超出 `[0, 1]` 范围的颜色分量值会产生未定义的结果。此色彩空间未进行伽马校正。

## 获取渲染模式

- **ColorRenderingMode.extendedLinear**：扩展线性 sRGB 工作色彩空间。

- **ColorRenderingMode.nonLinear**：非线性 sRGB 工作色彩空间。


---
source: https://developer.apple.com/documentation/SwiftUI/ColorRenderingMode/linear
crawled: 2025-12-03T06:32:16Z
---

# ColorRenderingMode.linear

**Case**

The linear sRGB working color space.

## Declaration

```swift
case linear
```

## Discussion

Color component values outside the range `[0, 1]` produce undefined results. This color space isn’t gamma corrected.

## Getting rendering modes

- **ColorRenderingMode.extendedLinear**: The extended linear sRGB working color space.
- **ColorRenderingMode.nonLinear**: The non-linear sRGB working color space.

