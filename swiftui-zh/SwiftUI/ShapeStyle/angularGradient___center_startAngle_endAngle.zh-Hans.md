--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/angularGradient(_:center:startAngle:endAngle:)

抓取时间：2025-12-01T11:13:59Z

---

# angularGradient(_:center:startAngle:endAngle:)

**类型方法**

一个角度渐变，它根据起始角度和结束角度之间的角度变化应用颜色函数，并以填充形状内的相对中心点为锚点。

## 声明

```swift
static func angularGradient(_ gradient: AnyGradient, center: UnitPoint = .center, startAngle: Angle, endAngle: Angle) -> some ShapeStyle

```

## 参数

- **gradient**：用于填充形状的渐变，提供颜色及其相对停止位置。

- **center**：渐变的相对中心，从单位空间映射到填充形状的边界矩形。

- **startAngle**：渐变起始角度。

- **endAngle**：渐变结束角度。

## 讨论

角度渐变也称为“圆锥”渐变。如果 `endAngle - startAngle > 2π`，则渐变仅绘制最后一个完整的转弯。如果 `endAngle - startAngle < 2π`，则渐变会使用由 `0` 和 `1` 处的渐变停止点定义的颜色填充缺失区域，并在缺失区域的中间位置进行过渡。

例如，用作背景的角度渐变：

```swift
ContentView()
    .background(.angularGradient(.red.gradient))
```

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 角度渐变

- **angularGradient(colors:center:startAngle:endAngle:)**：由一组颜色定义的角度渐变。

- **angularGradient(stops:center:startAngle:endAngle:)**：由一组颜色停止点定义的角度渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/angularGradient(_:center:startAngle:endAngle:)
crawled: 2025-12-01T11:13:59Z
---

# angularGradient(_:center:startAngle:endAngle:)

**Type Method**

An angular gradient, which applies the color function as the angle changes between the start and end angles, and anchored to a relative center point within the filled shape.

## Declaration

```swift
static func angularGradient(_ gradient: AnyGradient, center: UnitPoint = .center, startAngle: Angle, endAngle: Angle) -> some ShapeStyle

```

## Parameters

- **gradient**: The gradient to use for filling the shape, providing the colors and their relative stop locations.
- **center**: The relative center of the gradient, mapped from the unit space into the bounding rectangle of the filled shape.
- **startAngle**: The angle that marks the beginning of the gradient.
- **endAngle**: The angle that marks the end of the gradient.

## Discussion

An angular gradient is also known as a “conic” gradient. If `endAngle - startAngle > 2π`, the gradient only draws the last complete turn. If `endAngle - startAngle < 2π`, the gradient fills the missing area with the colors defined by gradient stop locations at `0` and `1`, transitioning between the two halfway across the missing area.

For example, an angular gradient used as a background:

```swift
ContentView()
    .background(.angularGradient(.red.gradient))
```

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Angular gradients

- **angularGradient(colors:center:startAngle:endAngle:)**: An angular gradient defined by a collection of colors.
- **angularGradient(stops:center:startAngle:endAngle:)**: An angular gradient defined by a collection of color stops.

