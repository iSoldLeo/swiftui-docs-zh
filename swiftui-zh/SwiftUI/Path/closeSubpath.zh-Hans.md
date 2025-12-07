---
来源： https://developer.apple.com/documentation/SwiftUI/Path/closeSubpath()
抓取时间： 2025-12-01T02:33:29Z
---

# closeSubpath()

**实例方法**

关闭并完成当前子路径。

## 声明

```swift
mutating func closeSubpath()
```

## 讨论

从当前点向当前子路径的起点添加一行，并结束子路径。

关闭子路径后，您的应用程序可以开始一个新的子路径，而无需首先调用 `move(to:)`。在这种情况下，将隐式创建一个新的子路径，其起点和当前点等于前一个子路径的起点。

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
- **addRect(_:transform:)**：为路径添加矩形子路径。
- **addRects(_:transform:)**：为路径添加一组矩形子路径。
- **addRelativeArc(center:radius:startAngle:delta:transform:)**：为路径添加圆弧，指定半径和角度差。
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加一个圆角矩形。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/closeSubpath()
crawled: 2025-12-01T02:33:29Z
---

# closeSubpath()

**Instance Method**

Closes and completes the current subpath.

## Declaration

```swift
mutating func closeSubpath()
```

## Discussion

Appends a line from the current point to the starting point of the current subpath and ends the subpath.

After closing the subpath, your application can begin a new subpath without first calling `move(to:)`. In this case, a new subpath is implicitly created with a starting and current point equal to the previous subpath’s starting point.

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
- **addRect(_:transform:)**: Adds a rectangular subpath to the path.
- **addRects(_:transform:)**: Adds a set of rectangular subpaths to the path.
- **addRelativeArc(center:radius:startAngle:delta:transform:)**: Adds an arc of a circle to the path, specified with a radius and a difference in angle.
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.

