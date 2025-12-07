--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/conicGradient(_:center:angle:)

抓取时间：2025-12-03T06:24:55Z

---

# conicGradient(_:center:angle:)

**类型方法**

一个圆锥渐变，完成一个完整的圆锥弧，可以选择从给定的角度开始，并以填充形状内的相对中心点为锚点。

## 声明

```swift
static func conicGradient(_ gradient: AnyGradient, center: UnitPoint = .center, angle: Angle = .zero) -> some ShapeStyle

```

## 参数

- **gradient**：用于填充形状的渐变，提供颜色及其相对停止位置。

- **center**：渐变的相对中心，从单位空间映射到填充形状的边界矩形。

- **angle**：渐变完整旋转起始点的偏移角度。

## 讨论

例如，用作背景的圆锥渐变：

```swift
let gradient = Gradient(colors: [.red, .yellow])

ContentView()
    .background(.conicGradient(gradient))
```

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 圆锥渐变

- **conicGradient(colors:center:angle:)**：由一组颜色定义并完成完整旋转的圆锥渐变。

- **conicGradient(stops:center:angle:)**：由一组颜色停止点定义并完成完整旋转的圆锥渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/conicGradient(_:center:angle:)
crawled: 2025-12-03T06:24:55Z
---

# conicGradient(_:center:angle:)

**Type Method**

A conic gradient that completes a full turn, optionally starting from a given angle and anchored to a relative center point within the filled shape.

## Declaration

```swift
static func conicGradient(_ gradient: AnyGradient, center: UnitPoint = .center, angle: Angle = .zero) -> some ShapeStyle

```

## Parameters

- **gradient**: The gradient to use for filling the shape, providing the colors and their relative stop locations.
- **center**: The relative center of the gradient, mapped from the unit space into the bounding rectangle of the filled shape.
- **angle**: The angle to offset the beginning of the gradient’s full turn.

## Discussion

For example, a conic gradient used as a background:

```swift
let gradient = Gradient(colors: [.red, .yellow])

ContentView()
    .background(.conicGradient(gradient))
```

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Conic gradients

- **conicGradient(colors:center:angle:)**: A conic gradient defined by a collection of colors that completes a full turn.
- **conicGradient(stops:center:angle:)**: A conic gradient defined by a collection of color stops that completes a full turn.

