---
来源： https://developer.apple.com/documentation/SwiftUI/Path/addLines(_:)
抓取时间： 2025-12-01T02:33:24Z
---

# addLines(_:)

**实例方法**

为路径添加一系列相连的直线段。

## 声明

```swift
mutating func addLines(_ lines: [CGPoint])
```

## 讨论

调用此便捷方法等同于对数组中的所有点进行变换，然后使用`move(to:)` 数组中的第一个值调用`points` 方法，再对后面的每个点调用`addLine(to:)` 方法，直到数组中的所有点都调用完为止。调用该方法后，路径的当前点就是数组中的最后一个点。

- 参数

- 行：指定要绘制的线段的起点和终点的数值数组。数组中的每个点都指定了用户空间中的一个位置。数组中的第一个点指定初始起点。
- 变换在添加到路径之前应用于点的仿射变换。如果未指定，默认为身份变换。

## 绘制路径

- **move(to:)**：从指定点开始绘制新的子路径。
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addArc(tangent1End:tangent2End:radius:transform:)**：为路径添加圆弧，指定半径和两条切线。
- **addCurve(to:control1:control2:)**：以指定的终点和控制点为路径添加一条三次贝塞尔曲线。
- **addEllipse(in:transform:)**：为路径添加一个适合指定矩形的椭圆。
- **addLine(to:)**：添加从当前点到指定点的直线段。
- **addPath(_:transform:)**：将另一个路径值附加到此路径。
- **addQuadCurve(to:control:)**：以指定的终点和控制点为路径添加一条二次贝塞尔曲线。
- **addRect(_:transform:)**：为路径添加矩形子路径。
- **addRects(_:transform:)**：为路径添加一组矩形子路径。
- **addRelativeArc(center:radius:startAngle:delta:transform:)**：为路径添加圆弧，指定半径和角度差。
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加圆角矩形。
- **closeSubpath()**：关闭并完成当前子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addLines(_:)
crawled: 2025-12-01T02:33:24Z
---

# addLines(_:)

**Instance Method**

Adds a sequence of connected straight-line segments to the path.

## Declaration

```swift
mutating func addLines(_ lines: [CGPoint])
```

## Discussion

Calling this convenience method is equivalent to applying the transform to all points in the array, then calling the `move(to:)` method with the first value in the `points` array, then calling the `addLine(to:)` method for each subsequent point until the array is exhausted. After calling this method, the path’s current point is the last point in the array.

- Parameter:

- lines: An array of values that specify the start and end points of the line segments to draw. Each point in the array specifies a position in user space. The first point in the array specifies the initial starting point.
- transform: An affine transform to apply to the points before adding to the path. Defaults to the identity transform if not specified.

## Drawing a path

- **move(to:)**: Begins a new subpath at the specified point.
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addArc(tangent1End:tangent2End:radius:transform:)**: Adds an arc of a circle to the path, specified with a radius and two tangent lines.
- **addCurve(to:control1:control2:)**: Adds a cubic Bézier curve to the path, with the specified end point and control points.
- **addEllipse(in:transform:)**: Adds an ellipse that fits inside the specified rectangle to the path.
- **addLine(to:)**: Appends a straight line segment from the current point to the specified point.
- **addPath(_:transform:)**: Appends another path value to this path.
- **addQuadCurve(to:control:)**: Adds a quadratic Bézier curve to the path, with the specified end point and control point.
- **addRect(_:transform:)**: Adds a rectangular subpath to the path.
- **addRects(_:transform:)**: Adds a set of rectangular subpaths to the path.
- **addRelativeArc(center:radius:startAngle:delta:transform:)**: Adds an arc of a circle to the path, specified with a radius and a difference in angle.
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **closeSubpath()**: Closes and completes the current subpath.

