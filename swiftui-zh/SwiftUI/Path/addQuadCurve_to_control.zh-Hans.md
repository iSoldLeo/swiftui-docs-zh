---
来源：https://developer.apple.com/documentation/SwiftUI/Path/addQuadCurve(to:control:)
抓取时间： 2025-12-02T21:42:30Z
---

# addQuadCurve(to:control:)

**实例方法**

以指定的终点和控制点为路径添加一条二次贝塞尔曲线。

## 声明

```swift
mutating func addQuadCurve(to end: CGPoint, control: CGPoint)
```

## 参数

- **control**：以用户空间坐标表示的曲线控制点。

## 讨论

本方法构造一条曲线，从路径的当前点开始，到指定的终点结束，曲率由控制点定义。本方法将曲线附加到当前路径后，曲线的终点就会成为路径的当前点。

## 绘制路径

- **move(to:)**：从指定点开始绘制新的子路径。
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addArc(tangent1End:tangent2End:radius:transform:)**：为路径添加圆弧，指定半径和两条切线。
- **addCurve(to:control1:control2:)**：以指定的终点和控制点为路径添加一条三次贝塞尔曲线。
- **addEllipse(in:transform:)**：为路径添加一个适合指定矩形的椭圆。
- **addLine(to:)**：添加从当前点到指定点的直线段。
- **addLines(_:)**：向路径添加一连串相连的直线段。
- **addPath(_:transform:)**：为该路径添加另一个路径值。
- **addRect(_:transform:)**：为路径添加一个矩形子路径。
- **addRects(_:transform:)**：为路径添加一组矩形子路径。
- **addRelativeArc(center:radius:startAngle:delta:transform:)**：为路径添加圆弧，指定半径和角度差。
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加圆角矩形。
- **closeSubpath()**：关闭并完成当前子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addQuadCurve(to:control:)
crawled: 2025-12-02T21:42:30Z
---

# addQuadCurve(to:control:)

**Instance Method**

Adds a quadratic Bézier curve to the path, with the specified end point and control point.

## Declaration

```swift
mutating func addQuadCurve(to end: CGPoint, control: CGPoint)
```

## Parameters

- **control**: The control point of the curve, in user space coordinates.

## Discussion

This method constructs a curve starting from the path’s current point and ending at the specified end point, with curvature defined by the control point. After this method appends that curve to the current path, the end point of the curve becomes the path’s current point.

## Drawing a path

- **move(to:)**: Begins a new subpath at the specified point.
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addArc(tangent1End:tangent2End:radius:transform:)**: Adds an arc of a circle to the path, specified with a radius and two tangent lines.
- **addCurve(to:control1:control2:)**: Adds a cubic Bézier curve to the path, with the specified end point and control points.
- **addEllipse(in:transform:)**: Adds an ellipse that fits inside the specified rectangle to the path.
- **addLine(to:)**: Appends a straight line segment from the current point to the specified point.
- **addLines(_:)**: Adds a sequence of connected straight-line segments to the path.
- **addPath(_:transform:)**: Appends another path value to this path.
- **addRect(_:transform:)**: Adds a rectangular subpath to the path.
- **addRects(_:transform:)**: Adds a set of rectangular subpaths to the path.
- **addRelativeArc(center:radius:startAngle:delta:transform:)**: Adds an arc of a circle to the path, specified with a radius and a difference in angle.
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **closeSubpath()**: Closes and completes the current subpath.

