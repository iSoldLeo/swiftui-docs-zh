---
来源： https://developer.apple.com/documentation/SwiftUI/Gradient/ColorSpace
抓取时间： 2025-12-03T06:25:37Z
---

# Gradient.ColorSpace

**Structure**

在渐变中对颜色进行内插的方法。

## 声明

```swift
struct ColorSpace
```

## 获取插值方法

- **device**：在输出色彩空间中插值渐变色。
- **perceptual**：在感知色彩空间中插值渐变色。

### 使用色彩空间

- **colorSpace(_:)**：返回使用指定色彩空间插值的渐变色版本。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Gradient/ColorSpace
crawled: 2025-12-03T06:25:37Z
---

# Gradient.ColorSpace

**Structure**

A method of interpolating between the colors in a gradient.

## Declaration

```swift
struct ColorSpace
```

## Getting an interpolation method

- **device**: Interpolates gradient colors in the output color space.
- **perceptual**: Interpolates gradient colors in a perceptual color space.

## Working with color spaces

- **colorSpace(_:)**: Returns a version of the gradient that will use a specified color space for interpolating between its colors.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

