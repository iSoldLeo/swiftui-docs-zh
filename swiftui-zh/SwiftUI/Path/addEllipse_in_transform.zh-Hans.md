---
来源：https://developer.apple.com/documentation/SwiftUI/Path/addEllipse(in:transform:)
抓取时间： 2025-12-01T02:33:22Z
---

# addEllipse(in:transform:)

**实例方法**

将适合指定矩形的椭圆添加到路径中。

## 声明

```swift
mutating func addEllipse(in rect: CGRect, transform: CGAffineTransform = .identity)
```

## 讨论

椭圆由一系列贝塞尔曲线逼近。它的中心是`rect` 参数定义的矩形的中点。如果矩形是正方形，那么椭圆就是半径等于矩形宽度（或高度）二分之一的圆形。如果`rect` 参数指定的是矩形，则椭圆的主轴和次轴由矩形的宽度和高度定义。

椭圆构成路径的完整子路径，也就是说，椭圆的绘制以移动到操作开始，以关闭子路径操作结束，所有移动都按顺时针方向进行。

- 参数

- rect（矩形一个矩形，用于定义椭圆所在的区域。
- 变换：在添加到路径之前应用于椭圆的仿射变换。如果未指定，默认为身份变换。

## 绘制路径

- **move(to:)**：从指定点开始绘制新的子路径。
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addArc(tangent1End:tangent2End:radius:transform:)**：为路径添加圆弧，指定半径和两条切线。
- **addCurve(to:control1:control2:)**：以指定的终点和控制点为路径添加一条三次贝塞尔曲线。
- **addLine(to:)**：添加一条从当前点到指定点的直线段。
- **addLines(_:)**：向路径添加一连串相连的直线段。
- **addPath(_:transform:)**：为该路径添加另一个路径值。
- **addQuadCurve(to:control:)**：以指定的终点和控制点为路径添加一条二次贝塞尔曲线。
- **addRect(_:transform:)**：为路径添加矩形子路径。
- **addRects(_:transform:)**：为路径添加一组矩形子路径。
- **addRelativeArc(center:radius:startAngle:delta:transform:)**：为路径添加圆弧，指定半径和角度差。
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加圆角矩形。
- **closeSubpath()**：关闭并完成当前子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addEllipse(in:transform:)
crawled: 2025-12-01T02:33:22Z
---

# addEllipse(in:transform:)

**Instance Method**

Adds an ellipse that fits inside the specified rectangle to the path.

## Declaration

```swift
mutating func addEllipse(in rect: CGRect, transform: CGAffineTransform = .identity)
```

## Discussion

The ellipse is approximated by a sequence of Bézier curves. Its center is the midpoint of the rectangle defined by the `rect` parameter. If the rectangle is square, then the ellipse is circular with a radius equal to one-half the width (or height) of the rectangle. If the `rect` parameter specifies a rectangular shape, then the major and minor axes of the ellipse are defined by the width and height of the rectangle.

The ellipse forms a complete subpath of the path— that is, the ellipse drawing starts with a move-to operation and ends with a close-subpath operation, with all moves oriented in the clockwise direction.

- Parameter:

- rect: A rectangle that defines the area for the ellipse to fit in.
- transform: An affine transform to apply to the ellipse before adding to the path. Defaults to the identity transform if not specified.

## Drawing a path

- **move(to:)**: Begins a new subpath at the specified point.
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addArc(tangent1End:tangent2End:radius:transform:)**: Adds an arc of a circle to the path, specified with a radius and two tangent lines.
- **addCurve(to:control1:control2:)**: Adds a cubic Bézier curve to the path, with the specified end point and control points.
- **addLine(to:)**: Appends a straight line segment from the current point to the specified point.
- **addLines(_:)**: Adds a sequence of connected straight-line segments to the path.
- **addPath(_:transform:)**: Appends another path value to this path.
- **addQuadCurve(to:control:)**: Adds a quadratic Bézier curve to the path, with the specified end point and control point.
- **addRect(_:transform:)**: Adds a rectangular subpath to the path.
- **addRects(_:transform:)**: Adds a set of rectangular subpaths to the path.
- **addRelativeArc(center:radius:startAngle:delta:transform:)**: Adds an arc of a circle to the path, specified with a radius and a difference in angle.
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **closeSubpath()**: Closes and completes the current subpath.

