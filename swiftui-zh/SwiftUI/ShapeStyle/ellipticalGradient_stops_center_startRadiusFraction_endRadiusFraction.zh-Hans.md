--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/ellipticalGradient(stops:center:startRadiusFraction:endRadiusFraction:)

抓取时间：2025-12-01T11:14:06Z

---

# ellipticalGradient(stops:center:startRadiusFraction:endRadiusFraction:)

**类型方法**

绘制由一系列颜色停止点定义的椭圆的径向渐变。

## 声明

```swift
static func ellipticalGradient(stops: [Gradient.Stop], center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5) -> EllipticalGradient
```

## 讨论

该渐变将其坐标空间映射到定义其中心和半径的单位空间正方形，然后拉伸该正方形以填充其边界矩形，也可能拉伸圆形渐变以使其具有椭圆轮廓。

例如，用作背景的椭圆渐变：

```swift
.background(.ellipticalGradient(stops: [
    .init(color: .red, location: 0.0),
    .init(color: .yellow, location: 0.9),
    .init(color: .yellow, location: 1.0),
]))
```

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 椭圆渐变

- **ellipticalGradient(_:center:startRadiusFraction:endRadiusFraction:)**：绘制椭圆的径向渐变。

- **ellipticalGradient(colors:center:startRadiusFraction:endRadiusFraction:)**：绘制由一组颜色定义的椭圆的径向渐变。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/ellipticalGradient(stops:center:startRadiusFraction:endRadiusFraction:)
crawled: 2025-12-01T11:14:06Z
---

# ellipticalGradient(stops:center:startRadiusFraction:endRadiusFraction:)

**Type Method**

A radial gradient that draws an ellipse defined by a collection of color stops.

## Declaration

```swift
static func ellipticalGradient(stops: [Gradient.Stop], center: UnitPoint = .center, startRadiusFraction: CGFloat = 0, endRadiusFraction: CGFloat = 0.5) -> EllipticalGradient
```

## Discussion

The gradient maps its coordinate space to the unit space square in which its center and radii are defined, then stretches that square to fill its bounding rect, possibly also stretching the circular gradient to have elliptical contours.

For example, an elliptical gradient used as a background:

```swift
.background(.ellipticalGradient(stops: [
    .init(color: .red, location: 0.0),
    .init(color: .yellow, location: 0.9),
    .init(color: .yellow, location: 1.0),
]))
```

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Elliptical gradients

- **ellipticalGradient(_:center:startRadiusFraction:endRadiusFraction:)**: A radial gradient that draws an ellipse.
- **ellipticalGradient(colors:center:startRadiusFraction:endRadiusFraction:)**: A radial gradient that draws an ellipse defined by a collection of colors.

