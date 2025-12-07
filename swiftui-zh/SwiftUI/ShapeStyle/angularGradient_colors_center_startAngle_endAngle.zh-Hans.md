--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/angularGradient(colors:center:startAngle:endAngle:)

抓取时间：2025-12-01T11:14:00Z

---

# angularGradient(colors:center:startAngle:endAngle:)

**类型方法**

由一组颜色定义的角度渐变。

## 声明

```swift
static func angularGradient(colors: [Color], center: UnitPoint, startAngle: Angle, endAngle: Angle) -> AngularGradient
```

## 参数

- **colors**：渐变的颜色，沿其全长均匀分布。

- **center**：渐变的相对中心，从单位空间映射到填充形状的边界矩形。

- **startAngle**：标记渐变起始角度的参数。

- **endAngle**：标记渐变结束角度的点。

## 讨论

有关如何使用角度渐变的更多信息，请参阅 [angularGradient(_:center:startAngle:endAngle:)](angularGradient___center_startAngle_endAngle.zh-Hans.md)。

## 角度渐变

- **angularGradient(_:center:startAngle:endAngle:)**：角度渐变，其颜色函数会随着起始角度和结束角度之间的变化而变化，并以填充形状内的相对中心点为锚点。

- **angularGradient(stops:center:startAngle:endAngle:)**：由一系列颜色停止点定义的角度渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/angularGradient(colors:center:startAngle:endAngle:)
crawled: 2025-12-01T11:14:00Z
---

# angularGradient(colors:center:startAngle:endAngle:)

**Type Method**

An angular gradient defined by a collection of colors.

## Declaration

```swift
static func angularGradient(colors: [Color], center: UnitPoint, startAngle: Angle, endAngle: Angle) -> AngularGradient
```

## Parameters

- **colors**: The colors of the gradient, evenly spaced along its full length.
- **center**: The relative center of the gradient, mapped from the unit space into the bounding rectangle of the filled shape.
- **startAngle**: The angle that marks the beginning of the gradient.
- **endAngle**: The angle that marks the end of the gradient.

## Discussion

For more information on how to use angular gradients, see [angularGradient(_:center:startAngle:endAngle:)](angularGradient___center_startAngle_endAngle.zh-Hans.md).

## Angular gradients

- **angularGradient(_:center:startAngle:endAngle:)**: An angular gradient, which applies the color function as the angle changes between the start and end angles, and anchored to a relative center point within the filled shape.
- **angularGradient(stops:center:startAngle:endAngle:)**: An angular gradient defined by a collection of color stops.

