---
来源：https://developer.apple.com/documentation/SwiftUI/Path/addPath(_:transform:)
抓取时间： 2025-12-02T21:42:29Z
---

# addPath(_:transform:)

**实例方法**

将另一个路径值添加到此路径中。

## 声明

```swift
mutating func addPath(_ path: Path, transform: CGAffineTransform = .identity)
```

## 参数

- **path**：要添加的路径。
- **transform**：路径参数的仿射变换。如果未指定，默认为身份变换。

## 讨论

如果`path`参数是一条非空的空路径，那么它的元素会依次追加到此路径中。之后，这条路径的起点和当前点就是`path`参数中最后一个子路径的起点和当前点。

## 绘制路径

- **move(to:)**：从指定点开始绘制新的子路径。
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：为路径添加圆弧，指定半径和角度。
- **addArc(tangent1End:tangent2End:radius:transform:)**：为路径添加圆弧，指定半径和两条切线。
- **addCurve(to:control1:control2:)**：以指定的终点和控制点为路径添加一条三次贝塞尔曲线。
- **addEllipse(in:transform:)**：为路径添加一个适合指定矩形的椭圆。
- **addLine(to:)**：添加从当前点到指定点的直线段。
- **addLines(_:)**：向路径添加一连串相连的直线段。
- **addQuadCurve(to:control:)**：以指定的终点和控制点为路径添加一条二次贝塞尔曲线。
- **addRect(_:transform:)**：为路径添加矩形子路径。
- **addRects(_:transform:)**：为路径添加一组矩形子路径。
- **addRelativeArc(center:radius:startAngle:delta:transform:)**：为路径添加圆弧，指定半径和角度差。
- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加圆角矩形。
- **closeSubpath()**：关闭并完成当前子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addPath(_:transform:)
crawled: 2025-12-02T21:42:29Z
---

# addPath(_:transform:)

**Instance Method**

Appends another path value to this path.

## Declaration

```swift
mutating func addPath(_ path: Path, transform: CGAffineTransform = .identity)
```

## Parameters

- **path**: The path to add.
- **transform**: An affine transform to apply to the path parameter before adding to this path. Defaults to the identity transform if not specified.

## Discussion

If the `path` parameter is a non-empty empty path, its elements are appended in order to this path. Afterward, the start point and current point of this path are those of the last subpath in the `path` parameter.

## Drawing a path

- **move(to:)**: Begins a new subpath at the specified point.
- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**: Adds an arc of a circle to the path, specified with a radius and angles.
- **addArc(tangent1End:tangent2End:radius:transform:)**: Adds an arc of a circle to the path, specified with a radius and two tangent lines.
- **addCurve(to:control1:control2:)**: Adds a cubic Bézier curve to the path, with the specified end point and control points.
- **addEllipse(in:transform:)**: Adds an ellipse that fits inside the specified rectangle to the path.
- **addLine(to:)**: Appends a straight line segment from the current point to the specified point.
- **addLines(_:)**: Adds a sequence of connected straight-line segments to the path.
- **addQuadCurve(to:control:)**: Adds a quadratic Bézier curve to the path, with the specified end point and control point.
- **addRect(_:transform:)**: Adds a rectangular subpath to the path.
- **addRects(_:transform:)**: Adds a set of rectangular subpaths to the path.
- **addRelativeArc(center:radius:startAngle:delta:transform:)**: Adds an arc of a circle to the path, specified with a radius and a difference in angle.
- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **closeSubpath()**: Closes and completes the current subpath.

