---
来源： https://developer.apple.com/documentation/SwiftUI/Path/Element/move(to:)
抓取时间： 2025-12-03T19:23:18Z
---

# Path.Element.move(to:)

**Case**

终止当前子路径（不关闭）并定义新的当前点的路径元素。

### 声明

```swift
case move(to: CGPoint)
```

## 获取路径元素

- **Path.Element.closeSubpath**：从当前子路径的起点（如果有）到当前点的直线，该点是子路径的终点。
- **Path.Element.curve(to:control1:control2:)**：从上一个当前点到给定端点的三次贝塞尔曲线，使用两个控制点来定义曲线。
- **Path.Element.line(to:)**：从上一个当前点到给定点的直线，该点成为新的当前点。
- **Path.Element.quadCurve(to:control:)**：从上一个当前点到给定端点的二次贝塞尔曲线，使用单个控制点定义曲线。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/Element/move(to:)
crawled: 2025-12-03T19:23:18Z
---

# Path.Element.move(to:)

**Case**

A path element that terminates the current subpath (without closing it) and defines a new current point.

## Declaration

```swift
case move(to: CGPoint)
```

## Getting path elements

- **Path.Element.closeSubpath**: A line from the start point of the current subpath (if any) to the current point, which terminates the subpath.
- **Path.Element.curve(to:control1:control2:)**: A cubic Bézier curve from the previous current point to the given end-point, using the two control points to define the curve.
- **Path.Element.line(to:)**: A line from the previous current point to the given point, which becomes the new current point.
- **Path.Element.quadCurve(to:control:)**: A quadratic Bézier curve from the previous current point to the given end-point, using the single control point to define the curve.

