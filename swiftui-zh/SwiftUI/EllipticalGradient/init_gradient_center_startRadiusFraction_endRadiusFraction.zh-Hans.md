---
来源：https://developer.apple.com/documentation/SwiftUI/EllipticalGradient/init(gradient:center:startRadiusFraction:endRadiusFraction:)
抓取时间： 2025-12-03T05:41:27Z
---

# init(gradient:center:startRadiusFraction:endRadiusFraction:)

**Initializer**

创建椭圆梯度。

## 声明

```swift
init(gradient: Gradient, center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5)
```

## 讨论

例如，以视图的顶角为中心的椭圆梯度：

```swift
EllipticalGradient(
    gradient: .init(colors: [.blue, .green]),
    center: .topLeading,
    startRadiusFraction: 0,
    endRadiusFraction: 1)
```

- 梯度：颜色及其参数位置。
- center：圆心：圆心，坐标为 [0, 1]。
- startRadiusFraction：起始半径分数：起始半径值，介于 0 和 1 之间的分数。0 表示中心点，1 表示单位圆的直径。
- endRadiusFraction：结束半径：末端半径值，介于 0 和 1 之间的分数。0 表示中心点，1 表示单位圆的直径。

## 创建椭圆梯度

- **init(colors:center:startRadiusFraction:endRadiusFraction:)**：从颜色集合中创建椭圆梯度。
- **init(stops:center:startRadiusFraction:endRadiusFraction:)**：从一组色块创建椭圆渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/EllipticalGradient/init(gradient:center:startRadiusFraction:endRadiusFraction:)
crawled: 2025-12-03T05:41:27Z
---

# init(gradient:center:startRadiusFraction:endRadiusFraction:)

**Initializer**

Creates an elliptical gradient.

## Declaration

```swift
init(gradient: Gradient, center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5)
```

## Discussion

For example, an elliptical gradient centered on the top-leading corner of the view:

```swift
EllipticalGradient(
    gradient: .init(colors: [.blue, .green]),
    center: .topLeading,
    startRadiusFraction: 0,
    endRadiusFraction: 1)
```

- gradient: The colors and their parametric locations.
- center: The center of the circle, in [0, 1] coordinates.
- startRadiusFraction: The start radius value, as a fraction between zero and one. Zero maps to the center point, one maps to the diameter of the unit circle.
- endRadiusFraction: The end radius value, as a fraction between zero and one. Zero maps to the center point, one maps to the diameter of the unit circle.

## Creating an elliptical gradient

- **init(colors:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient from a collection of colors.
- **init(stops:center:startRadiusFraction:endRadiusFraction:)**: Creates an elliptical gradient from a collection of color stops.

