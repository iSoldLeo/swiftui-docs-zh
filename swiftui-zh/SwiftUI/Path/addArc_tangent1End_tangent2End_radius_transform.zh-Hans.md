---
source: https://developer.apple.com/documentation/SwiftUI/Path/addArc(tangent1End:tangent2End:radius:transform:)
抓取时间：2025-12-01T02:33:21Z
---

# addArc(tangent1End:tangent2End:radius:transform:)

**实例方法**

为路径添加圆弧，指定半径和两条切线。

## 声明

```swift
mutating func addArc(tangent1End: CGPoint, tangent2End: CGPoint, radius: CGFloat, transform: CGAffineTransform = .identity)
```

## 参数

- **tangent1End**：在用户空间坐标中，用于构建弧线的第一条切线的终点。(这条切线的起点是路径的当前点）。
- **tangent2End**：在用户空间坐标中，用于构建弧线的第二条切线的终点。(这条切线的起点是 tangent1End 点）。
- **radius**：以用户空间坐标表示的圆弧半径。
- **transform**：在将弧添加到路径之前应用于弧的仿射变换。如果未指定，默认为身份变换。

## 讨论

此方法计算两条切线--第一条从当前点到 tangent1End 点，第二条从 `tangent1End` 点到 `tangent2End` 点--然后计算指定半径圆弧的起点和终点，使圆弧与两条切线相切。最后，该方法用一系列立方贝塞尔曲线逼近该圆弧，并将这些曲线附加到路径上。

如果弧的起点（即指定半径的圆必须与第一条切线相交才能与第二条切线相切的点）不是当前点，此方法会将一条直线段从当前点添加到弧的起点。

弧的终点（即指定半径的圆必须与第二条切线相交才能与第一条直线相切的点）将成为路径的新的当前点。

## 绘制路径

- **move(to:)**：从指定点开始绘制新的子路径。
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addCurve(to:control1:control2:)**：以指定的终点和控制点为路径添加一条三次贝塞尔曲线。
- **addEllipse(in:transform:)**：为路径添加一个适合指定矩形的椭圆。
- **addLine(to:)**：添加从当前点到指定点的直线段。
- **addLines(_:)**：向路径添加一连串相连的直线段。
- **addPath(_:transform:)**：为该路径添加另一个路径值。
- **addQuadCurve(to:control:)**：以指定的终点和控制点为路径添加一条二次贝塞尔曲线。
- **addRect(_:transform:)**：为路径添加矩形子路径。
- **addRects(_:transform:)**：为路径添加一组矩形子路径。
- **addRelativeArc(center:radius:startAngle:delta:transform:)**：为路径添加圆弧，指定半径和角度差。
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加圆角矩形。
- **closeSubpath()**：关闭并完成当前子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addArc(tangent1End:tangent2End:radius:transform:)
crawled: 2025-12-01T02:33:21Z
---

# addArc(tangent1End:tangent2End:radius:transform:)

**Instance Method**

Adds an arc of a circle to the path, specified with a radius and two tangent lines.

## Declaration

```swift
mutating func addArc(tangent1End: CGPoint, tangent2End: CGPoint, radius: CGFloat, transform: CGAffineTransform = .identity)
```

## Parameters

- **tangent1End**: The end point, in user space coordinates, for the first tangent line to be used in constructing the arc. (The start point for this tangent line is the path’s current point.)
- **tangent2End**: The end point, in user space coordinates, for the second tangent line to be used in constructing the arc. (The start point for this tangent line is the tangent1End point.)
- **radius**: The radius of the arc, in user space coordinates.
- **transform**: An affine transform to apply to the arc before adding to the path. Defaults to the identity transform if not specified.

## Discussion

This method calculates two tangent lines—the first from the current point to the tangent1End point, and the second from the `tangent1End` point to the `tangent2End` point—then calculates the start and end points for a circular arc of the specified radius such that the arc is tangent to both lines. Finally, this method approximates that arc with a sequence of cubic Bézier curves and appends those curves to the path.

If the starting point of the arc (that is, the point where a circle of the specified radius must meet the first tangent line in order to also be tangent to the second line) is not the current point, this method appends a straight line segment from the current point to the starting point of the arc.

The ending point of the arc (that is, the point where a circle of the specified radius must meet the second tangent line in order to also be tangent to the first line) becomes the new current point of the path.

## Drawing a path

- **move(to:)**: Begins a new subpath at the specified point.
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addCurve(to:control1:control2:)**: Adds a cubic Bézier curve to the path, with the specified end point and control points.
- **addEllipse(in:transform:)**: Adds an ellipse that fits inside the specified rectangle to the path.
- **addLine(to:)**: Appends a straight line segment from the current point to the specified point.
- **addLines(_:)**: Adds a sequence of connected straight-line segments to the path.
- **addPath(_:transform:)**: Appends another path value to this path.
- **addQuadCurve(to:control:)**: Adds a quadratic Bézier curve to the path, with the specified end point and control point.
- **addRect(_:transform:)**: Adds a rectangular subpath to the path.
- **addRects(_:transform:)**: Adds a set of rectangular subpaths to the path.
- **addRelativeArc(center:radius:startAngle:delta:transform:)**: Adds an arc of a circle to the path, specified with a radius and a difference in angle.
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **closeSubpath()**: Closes and completes the current subpath.

