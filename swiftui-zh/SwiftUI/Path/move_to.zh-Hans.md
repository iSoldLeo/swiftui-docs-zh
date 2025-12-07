---
来源： https://developer.apple.com/documentation/SwiftUI/Path/move(to:)
抓取时间： 2025-12-02T21:42:24Z
---

# move(to:)

**实例方法**

在指定点开始新的子路径。

## 声明

```swift
mutating func move(to end: CGPoint)
```

## 参数

- **end**：以用户空间坐标表示的新子路径的起始点。

## 讨论

指定的点将成为新子路径的起点。当前点将设置为该起点。

## 绘制路径

- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addArc(tangent1End:tangent2End:radius:transform:)**：为路径添加圆弧，指定半径和两条切线。
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
source: https://developer.apple.com/documentation/SwiftUI/Path/move(to:)
crawled: 2025-12-02T21:42:24Z
---

# move(to:)

**Instance Method**

Begins a new subpath at the specified point.

## Declaration

```swift
mutating func move(to end: CGPoint)
```

## Parameters

- **end**: The point, in user space coordinates, at which to start a new subpath.

## Discussion

The specified point becomes the start point of a new subpath. The current point is set to this start point.

## Drawing a path

- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addArc(tangent1End:tangent2End:radius:transform:)**: Adds an arc of a circle to the path, specified with a radius and two tangent lines.
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

