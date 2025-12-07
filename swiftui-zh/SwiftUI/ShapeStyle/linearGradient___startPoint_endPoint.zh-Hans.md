--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/linearGradient(_:startPoint:endPoint:)

抓取时间：2025-12-01T11:14:06Z

---

# linearGradient(_:startPoint:endPoint:)

**类型方法**

线性渐变。

## 声明

```swift
static func linearGradient(_ gradient: AnyGradient, startPoint: UnitPoint, endPoint: UnitPoint) -> some ShapeStyle

```

## 说明

渐变沿由起点和终点定义的轴应用颜色函数。渐变将单位空间点映射到填充了渐变的每个形状的边界矩形中。

例如，用作背景的线性渐变：

```swift
ContentView()
    .background(.linearGradient(.red.gradient,
        startPoint: .top, endPoint: .bottom))
```

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 线性渐变

- **linearGradient(colors:startPoint:endPoint:)**：由一组颜色定义的线性渐变。

- **linearGradient(stops:startPoint:endPoint:)**：由一组颜色停止点定义的线性渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/linearGradient(_:startPoint:endPoint:)
crawled: 2025-12-01T11:14:06Z
---

# linearGradient(_:startPoint:endPoint:)

**Type Method**

A linear gradient.

## Declaration

```swift
static func linearGradient(_ gradient: AnyGradient, startPoint: UnitPoint, endPoint: UnitPoint) -> some ShapeStyle

```

## Discussion

The gradient applies the color function along an axis, as defined by its start and end points. The gradient maps the unit space points into the bounding rectangle of each shape filled with the gradient.

For example, a linear gradient used as a background:

```swift
ContentView()
    .background(.linearGradient(.red.gradient,
        startPoint: .top, endPoint: .bottom))
```

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Linear gradients

- **linearGradient(colors:startPoint:endPoint:)**: A linear gradient defined by a collection of colors.
- **linearGradient(stops:startPoint:endPoint:)**: A linear gradient defined by a collection of color stops.

