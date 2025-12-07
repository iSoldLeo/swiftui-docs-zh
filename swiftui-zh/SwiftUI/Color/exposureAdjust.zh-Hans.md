---
来源： https://developer.apple.com/documentation/SwiftUI/Color/exposureAdjust(_:)
抓取时间： 2025-12-01T10:29:04Z
---

# exposureAdjust(_:)

**实例方法**

返回应用了曝光调整的新颜色。

## 声明

```swift
func exposureAdjust(_ stops: Double) -> Color
```

## 参数

- **stops**：要调整的曝光级别数。

## 返回值

应用曝光调整后的新颜色。

## 讨论

此函数通过将颜色的线性光表示乘以 `pow(2, stops)` 并调整其 HDR 内容余量，来调整颜色的曝光。

例如，系统黄色的亮度可增加两个曝光级别：

```swift
Color.yellow.exposureAdjust(2)
```

## 修改颜色

- **opacity(_:)**：将颜色的不透明度乘以给定的数值。
- **gradient**：返回颜色 `self` 的标准渐变效果。
- **mix(with:by:in:)**：返回按 `fraction` 指定的量与`rhs` 混合的 self 版本。
- **headroom(_:)**：创建具有指定 HDR 内容净空的新颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/exposureAdjust(_:)
crawled: 2025-12-01T10:29:04Z
---

# exposureAdjust(_:)

**Instance Method**

Returns a new color with an exposure adjustment applied.

## Declaration

```swift
func exposureAdjust(_ stops: Double) -> Color
```

## Parameters

- **stops**: The number of exposure levels to adjust by.

## Return Value

A new color with the exposure adjustment applied.

## Discussion

This function adjusts the exposure of a color by multipling its linear-light representation by `pow(2, stops)` and adjusting its HDR content headroom.

For example the system yellow color could have its brightness increased by two exposure levels:

```swift
Color.yellow.exposureAdjust(2)
```

## Modifying a color

- **opacity(_:)**: Multiplies the opacity of the color by the given amount.
- **gradient**: Returns the standard gradient for the color `self`.
- **mix(with:by:in:)**: Returns a version of self mixed with `rhs` by the amount specified by `fraction`.
- **headroom(_:)**: Creates a new color with specified HDR content headroom.

