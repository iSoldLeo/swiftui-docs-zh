--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/radialGradient(_:center:startRadius:endRadius:)

抓取时间：2025-12-03T06:25:02Z

---

# radialGradient(_:center:startRadius:endRadius:)

**类型方法**

径向渐变。

## 声明

```swift
static func radialGradient(_ gradient: AnyGradient, center: UnitPoint = .center, startRadius: CGFloat = 0, endRadius: CGFloat) -> some ShapeStyle

```

## 说明

该渐变应用颜色函数，颜色值以中心点为基准，并根据定义的起始半径和结束半径进行缩放。渐变将单位空间中心点映射到填充了渐变的每个形状的边界矩形中。

例如，用作背景的径向渐变：

```swift
ContentView()
    .background(.radialGradient(.red.gradient, endRadius: 100))
```

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 径向渐变

- **radialGradient(colors:center:startRadius:endRadius:)**：由一组颜色定义的径向渐变。

- **radialGradient(stops:center:startRadius:endRadius:)**：由一组颜色停止点定义的径向渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/radialGradient(_:center:startRadius:endRadius:)
crawled: 2025-12-03T06:25:02Z
---

# radialGradient(_:center:startRadius:endRadius:)

**Type Method**

A radial gradient.

## Declaration

```swift
static func radialGradient(_ gradient: AnyGradient, center: UnitPoint = .center, startRadius: CGFloat = 0, endRadius: CGFloat) -> some ShapeStyle

```

## Discussion

The gradient applies the color function as the distance from a center point, scaled to fit within the defined start and end radii. The gradient maps the unit space center point into the bounding rectangle of each shape filled with the gradient.

For example, a radial gradient used as a background:

```swift
ContentView()
    .background(.radialGradient(.red.gradient, endRadius: 100))
```

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Radial gradients

- **radialGradient(colors:center:startRadius:endRadius:)**: A radial gradient defined by a collection of colors.
- **radialGradient(stops:center:startRadius:endRadius:)**: A radial gradient defined by a collection of color stops.

