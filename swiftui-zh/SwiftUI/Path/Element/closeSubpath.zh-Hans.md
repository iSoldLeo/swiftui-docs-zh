---
来源： https://developer.apple.com/documentation/SwiftUI/Path/Element/closeSubpath
抓取时间： 2025-12-03T19:23:16Z
---

# Path.Element.closeSubpath

**Case**

从当前子路径（如果有）的起点到终止子路径的当前点的直线。

### 声明

```swift
case closeSubpath
```

## 讨论

关闭子路径后，当前点变得未定义。

## 获取路径元素

- **Path.Element.curve(to:control1:control2:)**：使用两个控制点定义一条从当前点到给定终点的三次贝塞尔曲线。
- **Path.Element.line(to:)**：从上一个当前点到给定点的直线，该点成为新的当前点。
- **Path.Element.move(to:)**：终止当前子路径（不关闭）并定义新的当前点的路径元素。
- **Path.Element.quadCurve(to:control:)**：从上一个当前点到给定终点的二次贝塞尔曲线，使用单个控制点定义曲线。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/Element/closeSubpath
crawled: 2025-12-03T19:23:16Z
---

# Path.Element.closeSubpath

**Case**

A line from the start point of the current subpath (if any) to the current point, which terminates the subpath.

## Declaration

```swift
case closeSubpath
```

## Discussion

After closing the subpath, the current point becomes undefined.

## Getting path elements

- **Path.Element.curve(to:control1:control2:)**: A cubic Bézier curve from the previous current point to the given end-point, using the two control points to define the curve.
- **Path.Element.line(to:)**: A line from the previous current point to the given point, which becomes the new current point.
- **Path.Element.move(to:)**: A path element that terminates the current subpath (without closing it) and defines a new current point.
- **Path.Element.quadCurve(to:control:)**: A quadratic Bézier curve from the previous current point to the given end-point, using the single control point to define the curve.

