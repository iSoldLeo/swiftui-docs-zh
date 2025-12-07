---
来源： https://developer.apple.com/documentation/SwiftUI/Path/addRect(_:transform:)
抓取时间：2025-12-01T02:33:26Z
---

# addRect(_:transform:)

**实例方法**

为路径添加一个矩形子路径。

## 声明

```swift
mutating func addRect(_ rect: CGRect, transform: CGAffineTransform = .identity)
```

## 参数

- **rect**：以用户空间坐标指定的矩形。
- **transform**：在添加到路径之前应用于矩形的仿射变换。如果未指定，默认为身份变换。

## 讨论

这是一个将矩形添加到路径的便捷函数，首先移动到左下角，然后逆时针添加线条创建矩形，最后关闭子路径。

## 绘制路径

- **move(to:)**：在指定点开始新的子路径。
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addArc(tangent1End:tangent2End:radius:transform:)**：为路径添加圆弧，指定半径和两条切线。
- **addCurve(to:control1:control2:)**：以指定的终点和控制点为路径添加一条三次贝塞尔曲线。
- **addEllipse(in:transform:)**：为路径添加一个适合指定矩形的椭圆。
- **addLine(to:)**：添加从当前点到指定点的直线段。
- **addLines(_:)**：向路径添加一连串相连的直线段。
- **addPath(_:transform:)**：为该路径添加另一个路径值。
- **addQuadCurve(to:control:)**：以指定的终点和控制点为路径添加一条二次贝塞尔曲线。
- **addRects(_:transform:)**：为路径添加一组矩形子路径。
- **addRelativeArc(center:radius:startAngle:delta:transform:)**：为路径添加圆弧，指定半径和角度差。
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加圆角矩形。
- **closeSubpath()**：关闭并完成当前子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addRect(_:transform:)
crawled: 2025-12-01T02:33:26Z
---

# addRect(_:transform:)

**Instance Method**

Adds a rectangular subpath to the path.

## Declaration

```swift
mutating func addRect(_ rect: CGRect, transform: CGAffineTransform = .identity)
```

## Parameters

- **rect**: A rectangle, specified in user space coordinates.
- **transform**: An affine transform to apply to the rectangle before adding to the path. Defaults to the identity transform if not specified.

## Discussion

This is a convenience function that adds a rectangle to a path, starting by moving to the bottom-left corner and then adding lines counter-clockwise to create a rectangle, closing the subpath.

## Drawing a path

- **move(to:)**: Begins a new subpath at the specified point.
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addArc(tangent1End:tangent2End:radius:transform:)**: Adds an arc of a circle to the path, specified with a radius and two tangent lines.
- **addCurve(to:control1:control2:)**: Adds a cubic Bézier curve to the path, with the specified end point and control points.
- **addEllipse(in:transform:)**: Adds an ellipse that fits inside the specified rectangle to the path.
- **addLine(to:)**: Appends a straight line segment from the current point to the specified point.
- **addLines(_:)**: Adds a sequence of connected straight-line segments to the path.
- **addPath(_:transform:)**: Appends another path value to this path.
- **addQuadCurve(to:control:)**: Adds a quadratic Bézier curve to the path, with the specified end point and control point.
- **addRects(_:transform:)**: Adds a set of rectangular subpaths to the path.
- **addRelativeArc(center:radius:startAngle:delta:transform:)**: Adds an arc of a circle to the path, specified with a radius and a difference in angle.
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **closeSubpath()**: Closes and completes the current subpath.

