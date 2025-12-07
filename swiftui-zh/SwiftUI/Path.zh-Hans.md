--- 来源：https://developer.apple.com/documentation/SwiftUI/Path

抓取时间：2025-12-02T16:22:33Z

---

# 路径

**Structure**

二维形状的轮廓。

## 声明

```swift
@frozen struct Path
```

## 创建路径

- **init()**：创建一个空路径。

- **init(_:)**：创建一个空路径，然后执行闭包添加其初始元素。

- **init(ellipseIn:)**：在给定的矩形内创建一个椭圆路径。

- **init(roundedRect:cornerRadius:style:)**：创建一个包含圆角矩形的路径。

- **init(roundedRect:cornerSize:style:)**：创建一个包含圆角矩形的路径。

- **init(roundedRect:cornerRadii:style:)**：创建一个由给定圆角矩形构成的路径，该圆角矩形的圆角半径可能不均匀。

## 获取路径的特征

- **boundingRect**：包含所有路径段的矩形。

- **cgPath**：表示路径中元素的不可变路径。

- **contains(_:eoFill:)**：如果路径包含指定的点，则返回 true。

- **currentPoint**：返回路径中的最后一个点，如果路径不包含任何点，则返回 nil。

- **description**：可用于通过 `init?(_:)` 重新创建路径的路径描述。

- **isEmpty**：布尔值，指示路径是否包含零个元素。

## 绘制路径

- **move(to:)**：从指定点开始绘制新的子路径。

- **addArc(center:radius:startAngle:endAngle:clockwise:transform:)**：向路径添加一段圆弧，指定半径和角度。

- **addArc(tangent1End:tangent2End:radius:transform:)**：向路径添加一段圆弧，指定半径和两条切线。

- **addCurve(to:control1:control2:)**：向路径添加一条三次贝塞尔曲线，指定端点和控制点。

- **addEllipse(in:transform:)**：向路径添加一个位于指定矩形内的椭圆。

- **addLine(to:)**：从当前点到指定点添加一条直线段。

- **addLines(_:)**：向路径添加一系列连接的直线段。

- **addPath(_:transform:)**：向此路径添加另一个路径值。

- **addQuadCurve(to:control:)**：向路径添加一条二次贝塞尔曲线，其端点和控制点均已指定。

- **addRect(_:transform:)**：向路径添加一个矩形子路径。

- **addRects(_:transform:)**：向路径添加一组矩形子路径。

- **addRelativeArc(center:radius:startAngle:delta:transform:)**：向路径添加一个圆弧，其半径和角度差均已指定。

- **addRoundedRect(in:cornerSize:style:transform:)**：向路径添加一个圆角矩形。

- **closeSubpath()**：闭合并完成当前子路径。

## 路径变换

- **applying(_:)**：返回一个通过对路径的所有点应用变换而构造的路径。

- **offsetBy(dx:dy:)**：返回一个通过平移其所有点而构造的路径。

- **trimmedPath(from:to:)**：返回路径的部分副本。

## 对路径执行操作

- **addRoundedRect(in:cornerSize:style:transform:)**：向路径添加一个圆角矩形。

- **intersection(_:eoFill:)**：返回一个新路径，其中包含两个路径共有的填充区域。

- **lineIntersection(_:eoFill:)**：返回一条新路径，其中包含一条来自当前路径且与给定路径的填充区域重叠的线段。

- **lineSubtraction(_:eoFill:)**：返回一条新路径，其中包含一条来自当前路径且与给定路径的填充区域不重叠的线段。

- **normalized(eoFill:)**：返回此路径的一个新的弱简单副本。

- **subtracting(_:eoFill:)**：返回一条新路径，其中包含来自当前路径但不在给定路径中的填充区域。

- **symmetricDifference(_:eoFill:)**：返回一条新路径，其中包含来自当前路径或给定路径的填充区域，但不会同时出现在两者中。

- **union(_:eoFill:)**：返回一条新路径，其中包含来自当前路径或给定路径的填充区域。

## 操作路径元素

- **forEach(_:)**：调用 `body` 并传入路径中的每个元素。

- **Path.Element**：路径中的一个元素。

## 应用样式

- **strokedPath(_:)**：使用 `style` 定义描边轮廓的创建方式，返回路径的描边副本。

## 实例方法

- **addRoundedRect(in:cornerRadii:style:transform:)**：向路径添加一个圆角矩形，圆角不规则。

## 符合以下标准

- Animatable

- Copyable

- CustomStringConvertible

- Equatable

- LosslessStringConvertible

- Sendable

- SendableMetatype

- Shape

- View


---
source: https://developer.apple.com/documentation/SwiftUI/Path
crawled: 2025-12-02T16:22:33Z
---

# Path

**Structure**

The outline of a 2D shape.

## Declaration

```swift
@frozen struct Path
```

## Creating a path

- **init()**: Creates an empty path.
- **init(_:)**: Creates an empty path, then executes a closure to add its initial elements.
- **init(ellipseIn:)**: Creates a path as an ellipse within the given rectangle.
- **init(roundedRect:cornerRadius:style:)**: Creates a path containing a rounded rectangle.
- **init(roundedRect:cornerSize:style:)**: Creates a path containing a rounded rectangle.
- **init(roundedRect:cornerRadii:style:)**: Creates a path as the given rounded rectangle, which may have uneven corner radii.

## Getting the path’s characteristics

- **boundingRect**: A rectangle containing all path segments.
- **cgPath**: An immutable path representing the elements in the path.
- **contains(_:eoFill:)**: Returns true if the path contains a specified point.
- **currentPoint**: Returns the last point in the path, or nil if the path contains no points.
- **description**: A description of the path that may be used to recreate the path via `init?(_:)`.
- **isEmpty**: A Boolean value indicating whether the path contains zero elements.

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
- **closeSubpath()**: Closes and completes the current subpath.

## Transforming the path

- **applying(_:)**: Returns a path constructed by applying the transform to all points of the path.
- **offsetBy(dx:dy:)**: Returns a path constructed by translating all its points.
- **trimmedPath(from:to:)**: Returns a partial copy of the path.

## Performing operations on the path

- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **intersection(_:eoFill:)**: Returns a new path with filled regions common to both paths.
- **lineIntersection(_:eoFill:)**: Returns a new path with a line from this path that overlaps the filled regions of the given path.
- **lineSubtraction(_:eoFill:)**: Returns a new path with a line from this path that does not overlap the filled region of the given path.
- **normalized(eoFill:)**: Returns a new weakly-simple copy of this path.
- **subtracting(_:eoFill:)**: Returns a new path with filled regions from this path that are not in the given path.
- **symmetricDifference(_:eoFill:)**: Returns a new path with filled regions either from this path or the given path, but not in both.
- **union(_:eoFill:)**: Returns a new path with filled regions in either this path or the given path.

## Operating over path elements

- **forEach(_:)**: Calls `body` with each element in the path.
- **Path.Element**: An element of a path.

## Applying a style

- **strokedPath(_:)**: Returns a stroked copy of the path using `style` to define how the stroked outline is created.

## Instance Methods

- **addRoundedRect(in:cornerRadii:style:transform:)**: Adds a rounded rectangle with uneven corners to the path.

## Conforms To

- Animatable
- Copyable
- CustomStringConvertible
- Equatable
- LosslessStringConvertible
- Sendable
- SendableMetatype
- Shape
- View

