---
来源：https://developer.apple.com/documentation/SwiftUI/EllipticalGradient/init(colors:center:startRadiusFraction:endRadiusFraction:)
抓取时间：2025-12-03T05:41:28Z
---

# init(colors:center:startRadiusFraction:endRadiusFraction:)

**Initializer**

从颜色集合中创建椭圆梯度。

## 声明

```swift
init(colors: [Color], center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5)
```

## 讨论

例如，以视图的顶角为中心的椭圆梯度：

```swift
EllipticalGradient(
    colors: [.blue, .green],
    center: .topLeading,
    startRadiusFraction: 0,
    endRadiusFraction: 1)
```

- 颜色颜色，在整个渐变中均匀分布。
- center：圆心：圆心，坐标为 [0, 1]。
- startRadiusFraction：起始半径分数：起始半径值，介于 0 和 1 之间的分数。0 表示中心点，1 表示单位圆的直径。
- endRadiusFraction：结束半径：末端半径值，介于 0 和 1 之间的分数。0 表示中心点，1 表示单位圆的直径。

## 创建椭圆梯度

- **init(gradient:center:startRadiusFraction:endRadiusFraction:)**：创建椭圆梯度。
- **init(stops:center:startRadiusFraction:endRadiusFraction:)**：从一系列色块中创建椭圆渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/EllipticalGradient/init(colors:center:startRadiusFraction:endRadiusFraction:)
crawled: 2025-12-03T05:41:28Z
---

# init(colors:center:startRadiusFraction:endRadiusFraction:)

**Initializer**

Creates an elliptical gradient from a collection of colors.

## Declaration

```swift
init(colors: [Color], center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5)
```

## Discussion

For example, an elliptical gradient centered on the top-leading corner of the view:

```swift
EllipticalGradient(
    colors: [.blue, .green],
    center: .topLeading,
    startRadiusFraction: 0,
    endRadiusFraction: 1)
```

- colors: The colors, evenly distributed throughout the gradient.
- center: The center of the circle, in [0, 1] coordinates.
- startRadiusFraction: The start radius value, as a fraction between zero and one. Zero maps to the center point, one maps to the diameter of the unit circle.
- endRadiusFraction: The end radius value, as a fraction between zero and one. Zero maps to the center point, one maps to the diameter of the unit circle.

## Creating an elliptical gradient

- **init(gradient:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient.
- **init(stops:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient from a collection of color stops.

