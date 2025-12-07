---
来源：https://developer.apple.com/documentation/SwiftUI/Path/addRelativeArc(center:radius:startAngle:delta:transform:)
抓取时间： 2025-12-02T21:42:33Z


# addRelativeArc(center:radius:startAngle:delta:transform:)

**实例方法**

使用半径和角度差值将圆弧添加到路径上。

## 声明

```swift
mutating func addRelativeArc(center: CGPoint, radius: CGFloat, startAngle: Angle, delta: Angle, transform: CGAffineTransform = .identity)
```

## 参数

- **center**：以用户空间坐标表示的弧中心。
- **radius**：以用户空间坐标表示的圆弧半径。
- **startAngle**：与弧线起点的夹角，从正 x 轴测量。
- **delta**：圆弧的起始角和终止角之差。正值表示逆时针方向的弧线（在用户空间坐标中），反之亦然。
- **transform**：在添加到路径之前应用于弧的仿射变换。如果未指定，默认为身份变换。/

## 讨论

此方法使用您指定的半径和角度计算起点和终点，使用一系列三次贝塞尔曲线逼近这些点之间的一段圆，然后将这些曲线附加到路径上。

`delta`参数决定弧的长度和创建弧的方向；最终路径的实际方向取决于`transform`参数和绘制路径的上下文的当前变换。不过，由于 SwiftUI 默认使用垂直翻转坐标系（原点位于视图的左上方），因此指定顺时针方向的弧线会在应用变换后产生逆时针方向的弧线。

如果路径以未闭合的子路径结束，此方法会添加一条连接当前点和弧起点的线。如果没有未封闭的子路径，此方法会创建一个新的子路径，其起点就是弧的起点。弧的终点将成为路径的新当前点。

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
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加一个圆角矩形。
- **closeSubpath()**：关闭并完成当前子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addRelativeArc(center:radius:startAngle:delta:transform:)
crawled: 2025-12-02T21:42:33Z
---

# addRelativeArc(center:radius:startAngle:delta:transform:)

**Instance Method**

Adds an arc of a circle to the path, specified with a radius and a difference in angle.

## Declaration

```swift
mutating func addRelativeArc(center: CGPoint, radius: CGFloat, startAngle: Angle, delta: Angle, transform: CGAffineTransform = .identity)
```

## Parameters

- **center**: The center of the arc, in user space coordinates.
- **radius**: The radius of the arc, in user space coordinates.
- **startAngle**: The angle to the starting point of the arc, measured from the positive x-axis.
- **delta**: The difference between the starting angle and ending angle of the arc. A positive value creates a counter- clockwise arc (in user space coordinates), and vice versa.
- **transform**: An affine transform to apply to the arc before adding to the path. Defaults to the identity transform if not specified. /

## Discussion

This method calculates starting and ending points using the radius and angles you specify, uses a sequence of cubic Bézier curves to approximate a segment of a circle between those points, and then appends those curves to the path.

The `delta` parameter determines both the length of the arc the direction in which the arc is created; the actual direction of the final path is dependent on the `transform` parameter and the current transform of a context where the path is drawn. However, because SwiftUI by default uses a vertically-flipped coordinate system (with the origin in the top-left of the view), specifying a clockwise arc results in a counterclockwise arc after the transformation is applied.

If the path ends with an unclosed subpath, this method adds a line connecting the current point to the starting point of the arc. If there is no unclosed subpath, this method creates a new subpath whose starting point is the starting point of the arc. The ending point of the arc becomes the new current point of the path.

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
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **closeSubpath()**: Closes and completes the current subpath.

