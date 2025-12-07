---
来源： https://developer.apple.com/documentation/SwiftUI/Color/gradient
抓取时间： 2025-12-03T05:39:53Z
---

# 梯度

**实例属性**

返回颜色 `self` 的标准梯度。

## 声明

```swift
var gradient: AnyGradient { get }
```

## 讨论

例如，用从标准蓝色中提取的渐变色填充一个矩形：

```swift
Rectangle().fill(.blue.gradient)
```

## 修改颜色

- **opacity(_:)**：将颜色的不透明度乘以给定的数值。
- **mix(with:by:in:)**：返回自己与`rhs` 混合后的`fraction` 版本，混合量由`fraction` 指定。
- **exposureAdjust(_:)**：返回已应用曝光调整的新颜色。
- **headroom(_:)**：创建具有指定 HDR 内容余量的新颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/gradient
crawled: 2025-12-03T05:39:53Z
---

# gradient

**Instance Property**

Returns the standard gradient for the color `self`.

## Declaration

```swift
var gradient: AnyGradient { get }
```

## Discussion

For example, filling a rectangle with a gradient derived from the standard blue color:

```swift
Rectangle().fill(.blue.gradient)
```

## Modifying a color

- **opacity(_:)**: Multiplies the opacity of the color by the given amount.
- **mix(with:by:in:)**: Returns a version of self mixed with `rhs` by the amount specified by `fraction`.
- **exposureAdjust(_:)**: Returns a new color with an exposure adjustment applied.
- **headroom(_:)**: Creates a new color with specified HDR content headroom.

