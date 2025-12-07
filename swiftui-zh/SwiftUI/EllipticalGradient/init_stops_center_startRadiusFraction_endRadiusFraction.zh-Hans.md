---
来源：https://developer.apple.com/documentation/SwiftUI/EllipticalGradient/init(stops:center:startRadiusFraction:endRadiusFraction:)
抓取时间： 2025-12-03T05:41:28Z
---

# init(stops:center:startRadiusFraction:endRadiusFraction:)

**Initializer**

从颜色止点集合创建椭圆梯度。

## 声明

```swift
init(stops: [Gradient.Stop], center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5)
```

## 讨论

例如，一个椭圆梯度以视图的顶角为中心，并带有一些额外的绿色区域：

```swift
EllipticalGradient(
    stops: [
        .init(color: .blue, location: 0.0),
        .init(color: .green, location: 0.9),
        .init(color: .green, location: 1.0),
    ],
    center: .topLeading,
    startRadiusFraction: 0,
    endRadiusFraction: 1)
```

- 停止：颜色及其参数位置。
- center：圆心：圆心，坐标为 [0, 1]。
- startRadiusFraction：起始半径分数：起始半径值，介于 0 和 1 之间的分数。0 表示中心点，1 表示单位圆的直径。
- endRadiusFraction：结束半径：末端半径值，介于 0 和 1 之间的分数。0 表示中心点，1 表示单位圆的直径。

## 创建椭圆梯度

- **init(gradient:center:startRadiusFraction:endRadiusFraction:)**：创建椭圆梯度。
- **init(colors:center:startRadiusFraction:endRadiusFraction:)**：从颜色集合创建椭圆渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/EllipticalGradient/init(stops:center:startRadiusFraction:endRadiusFraction:)
crawled: 2025-12-03T05:41:28Z
---

# init(stops:center:startRadiusFraction:endRadiusFraction:)

**Initializer**

Creates an elliptical gradient from a collection of color stops.

## Declaration

```swift
init(stops: [Gradient.Stop], center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5)
```

## Discussion

For example, an elliptical gradient centered on the top-leading corner of the view, with some extra green area:

```swift
EllipticalGradient(
    stops: [
        .init(color: .blue, location: 0.0),
        .init(color: .green, location: 0.9),
        .init(color: .green, location: 1.0),
    ],
    center: .topLeading,
    startRadiusFraction: 0,
    endRadiusFraction: 1)
```

- stops: The colors and their parametric locations.
- center: The center of the circle, in [0, 1] coordinates.
- startRadiusFraction: The start radius value, as a fraction between zero and one. Zero maps to the center point, one maps to the diameter of the unit circle.
- endRadiusFraction: The end radius value, as a fraction between zero and one. Zero maps to the center point, one maps to the diameter of the unit circle.

## Creating an elliptical gradient

- **init(gradient:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient.
- **init(colors:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient from a collection of colors.

