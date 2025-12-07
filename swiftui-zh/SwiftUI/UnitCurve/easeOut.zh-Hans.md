---
来源： https://developer.apple.com/documentation/SwiftUI/UnitCurve/easeOut
抓取时间： 2025-12-03T06:14:39Z
---

# easeOut

**类型属性**

一条贝塞尔曲线，开始时速度很快，接近终点时速度减慢。

## 声明

```swift
static let easeOut: UnitCurve
```

## 讨论

起点和终点控制点分别位于 (x: 0, y: 0) 和 (x: 0.58, y: 1)。

## 获取缓和曲线

- **easeIn**：贝塞尔曲线，开始时速度较慢，结束时速度加快。
- **easeInOut**：一条贝塞尔曲线，开始时速度较慢，中间时速度加快，接近终点时速度再次减慢。
- **circularEaseIn**：开始时速度较慢，结束时速度加快的曲线。
- **circularEaseOut**：开始时速度很快，接近终点时速度减慢的圆曲线。
- **circularEaseInOut**：开始时速度较慢，在中间时速度加快，然后在接近终点时速度再次减慢的圆曲线。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve/easeOut
crawled: 2025-12-03T06:14:39Z
---

# easeOut

**Type Property**

A bezier curve that starts out quickly, then slows down as it approaches the end.

## Declaration

```swift
static let easeOut: UnitCurve
```

## Discussion

The start and end control points are located at (x: 0, y: 0) and (x: 0.58, y: 1).

## Getting easing curves

- **easeIn**: A bezier curve that starts out slowly, then speeds up as it finishes.
- **easeInOut**: A bezier curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.
- **circularEaseIn**: A curve that starts out slowly, then speeds up as it finishes.
- **circularEaseOut**: A circular curve that starts out quickly, then slows down as it approaches the end.
- **circularEaseInOut**: A circular curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.

