---
来源：https://developer.apple.com/documentation/SwiftUI/UnitCurve/bezier(startControlPoint:endControlPoint:)
抓取时间： 2025-12-03T06:14:43Z
---

# bezier(startControlPoint:endControlPoint:)

**类型方法**

使用贝塞尔控制点创建新曲线。

## 声明

```swift
static func bezier(startControlPoint: UnitPoint, endControlPoint: UnitPoint) -> UnitCurve
```

## 参数

- **startControlPoint**：与曲线起点 (0, 0) 相关联的立方贝塞尔控制点。从起点到控制点的切向量定义了时序函数的初始速度。
- **endControlPoint**：与曲线端点 (1, 1) 相关的立方贝塞尔控制点。从端点到控制点的切向量定义了时序函数的最终速度。

## 讨论

曲线求值时，控制点的 x 分量被箝位在 [0,1] 范围内。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve/bezier(startControlPoint:endControlPoint:)
crawled: 2025-12-03T06:14:43Z
---

# bezier(startControlPoint:endControlPoint:)

**Type Method**

Creates a new curve using bezier control points.

## Declaration

```swift
static func bezier(startControlPoint: UnitPoint, endControlPoint: UnitPoint) -> UnitCurve
```

## Parameters

- **startControlPoint**: The cubic Bézier control point associated with the curve’s start point at (0, 0). The tangent vector from the start point to its control point defines the initial velocity of the timing function.
- **endControlPoint**: The cubic Bézier control point associated with the curve’s end point at (1, 1). The tangent vector from the end point to its control point defines the final velocity of the timing function.

## Discussion

The x components of the control points are clamped to the range [0,1] when the curve is evaluated.

