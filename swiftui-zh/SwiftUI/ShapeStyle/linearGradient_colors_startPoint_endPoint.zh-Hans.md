--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/linearGradient(colors:startPoint:endPoint:)

抓取时间：2025-12-03T06:25:01Z

---

# linearGradient(colors:startPoint:endPoint:)

**类型方法**

由一组颜色定义的线性渐变。

## 声明

```swift
static func linearGradient(colors: [Color], startPoint: UnitPoint, endPoint: UnitPoint) -> LinearGradient
```

## 说明

渐变沿由起点和终点定义的轴应用颜色函数。渐变将单位空间点映射到填充了渐变的每个形状的边界矩形中。

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 线性渐变

- **linearGradient(_:startPoint:endPoint:)**：线性渐变。

- **linearGradient(stops:startPoint:endPoint:)**：由一系列颜色停止点定义的线性渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/linearGradient(colors:startPoint:endPoint:)
crawled: 2025-12-03T06:25:01Z
---

# linearGradient(colors:startPoint:endPoint:)

**Type Method**

A linear gradient defined by a collection of colors.

## Declaration

```swift
static func linearGradient(colors: [Color], startPoint: UnitPoint, endPoint: UnitPoint) -> LinearGradient
```

## Discussion

The gradient applies the color function along an axis, as defined by its start and end points. The gradient maps the unit space points into the bounding rectangle of each shape filled with the gradient.

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Linear gradients

- **linearGradient(_:startPoint:endPoint:)**: A linear gradient.
- **linearGradient(stops:startPoint:endPoint:)**: A linear gradient defined by a collection of color stops.

