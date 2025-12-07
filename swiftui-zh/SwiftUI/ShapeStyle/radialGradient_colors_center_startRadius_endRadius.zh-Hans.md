--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/radialGradient(colors:center:startRadius:endRadius:)

抓取时间：2025-12-01T11:14:10Z

---

# radialGradient(colors:center:startRadius:endRadius:)

**类型方法**

由一组颜色定义的径向渐变。

## 声明

```swift
static func radialGradient(colors: [Color], center: UnitPoint, startRadius: CGFloat, endRadius: CGFloat) -> RadialGradient
```

## 说明

该渐变应用颜色函数，颜色值以中心点为基准，并根据定义的起始半径和结束半径进行缩放。渐变将单位空间中心点映射到填充了渐变的每个形状的边界矩形上。

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 径向渐变

- **radialGradient(_:center:startRadius:endRadius:)**：径向渐变。

- **radialGradient(stops:center:startRadius:endRadius:)**：由一系列颜色停止点定义的径向渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/radialGradient(colors:center:startRadius:endRadius:)
crawled: 2025-12-01T11:14:10Z
---

# radialGradient(colors:center:startRadius:endRadius:)

**Type Method**

A radial gradient defined by a collection of colors.

## Declaration

```swift
static func radialGradient(colors: [Color], center: UnitPoint, startRadius: CGFloat, endRadius: CGFloat) -> RadialGradient
```

## Discussion

The gradient applies the color function as the distance from a center point, scaled to fit within the defined start and end radii. The gradient maps the unit space center point into the bounding rectangle of each shape filled with the gradient.

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Radial gradients

- **radialGradient(_:center:startRadius:endRadius:)**: A radial gradient.
- **radialGradient(stops:center:startRadius:endRadius:)**: A radial gradient defined by a collection of color stops.

