--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/conicGradient(stops:center:angle:)

抓取时间：2025-12-03T06:24:57Z

---

# conicGradient(stops:center:angle:)

**类型方法**

由一系列颜色停止点定义的圆锥渐变，完成一个完整的圆锥。

## 声明

```swift
static func conicGradient(stops: [Gradient.Stop], center: UnitPoint, angle: Angle = .zero) -> AngularGradient
```

## 参数

- **stops**：渐变的颜色停止点，定义每个分量颜色及其沿渐变全长的相对位置。

- **center**：渐变的相对中心，从单位空间映射到填充形状的边界矩形。

- **angle**：渐变完整旋转起始点的偏移角度。

## 讨论

有关如何使用圆锥渐变的更多信息，请参阅 [conicGradient(_:center:angle:)](conicGradient___center_angle.zh-Hans.md)。

## 圆锥渐变

- **conicGradient(_:center:angle:)**：完成完整旋转的圆锥渐变，可选择从给定角度开始，并锚定到填充形状内的相对中心点。

- **conicGradient(colors:center:angle:)**：由一组颜色定义的完成完整旋转的圆锥渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/conicGradient(stops:center:angle:)
crawled: 2025-12-03T06:24:57Z
---

# conicGradient(stops:center:angle:)

**Type Method**

A conic gradient defined by a collection of color stops that completes a full turn.

## Declaration

```swift
static func conicGradient(stops: [Gradient.Stop], center: UnitPoint, angle: Angle = .zero) -> AngularGradient
```

## Parameters

- **stops**: The color stops of the gradient, defining each component color and their relative location along the gradient’s full length.
- **center**: The relative center of the gradient, mapped from the unit space into the bounding rectangle of the filled shape.
- **angle**: The angle to offset the beginning of the gradient’s full turn.

## Discussion

For more information on how to use conic gradients, see [conicGradient(_:center:angle:)](conicGradient___center_angle.zh-Hans.md).

## Conic gradients

- **conicGradient(_:center:angle:)**: A conic gradient that completes a full turn, optionally starting from a given angle and anchored to a relative center point within the filled shape.
- **conicGradient(colors:center:angle:)**: A conic gradient defined by a collection of colors that completes a full turn.

