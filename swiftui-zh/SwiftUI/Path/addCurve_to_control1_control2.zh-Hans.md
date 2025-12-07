---
来源：https://developer.apple.com/documentation/SwiftUI/Path/addCurve(to:control1:control2:)
抓取时间： 2025-12-01T02:33:22Z
---

# addCurve(to:control1:control2:)

**实例方法**

使用指定的终点和控制点为路径添加一条三次贝塞尔曲线。

## 声明

```swift
mutating func addCurve(to end: CGPoint, control1: CGPoint, control2: CGPoint)
```

## 参数

- **control1**：曲线的第一个控制点，以用户空间坐标表示。
- **control2**：曲线的第二个控制点，以用户空间坐标表示。

### 讨论

本方法会构建一条从路径的当前点开始到指定终点结束的曲线，其曲率由两个控制点定义。本方法将该曲线附加到当前路径后，曲线的终点将成为路径的当前点。

## 绘制路径

- **move(to:)**：从指定点开始绘制新的子路径。
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addArc(tangent1End:tangent2End:radius:transform:)**：为路径添加圆弧，指定半径和两条切线。
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
source: https://developer.apple.com/documentation/SwiftUI/Path/addCurve(to:control1:control2:)
crawled: 2025-12-01T02:33:22Z
---

# addCurve(to:control1:control2:)

**Instance Method**

Adds a cubic Bézier curve to the path, with the specified end point and control points.

## Declaration

```swift
mutating func addCurve(to end: CGPoint, control1: CGPoint, control2: CGPoint)
```

## Parameters

- **control1**: The first control point of the curve, in user space coordinates.
- **control2**: The second control point of the curve, in user space coordinates.

## Discussion

This method constructs a curve starting from the path’s current point and ending at the specified end point, with curvature defined by the two control points. After this method appends that curve to the current path, the end point of the curve becomes the path’s current point.

## Drawing a path

- **move(to:)**: Begins a new subpath at the specified point.
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addArc(tangent1End:tangent2End:radius:transform:)**: Adds an arc of a circle to the path, specified with a radius and two tangent lines.
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

