---
来源： https://developer.apple.com/documentation/SwiftUI/UnitCurve/easeIn
抓取时间： 2025-12-03T06:14:38Z
---

# 缓解

**类型属性**

一条贝塞尔曲线，开始时速度较慢，结束时速度加快。

## 声明

```swift
static let easeIn: UnitCurve
```

## 讨论

起点和终点控制点分别位于 (x: 0.42, y: 0) 和 (x: 1, y: 1)。

## 获取缓和曲线

- **easeOut**：一条贝塞尔曲线，开始时速度很快，接近终点时速度减慢。
- **easeInOut**：开始时速度较慢，中间时速度加快，接近终点时速度再次减慢的贝塞尔曲线。
- **circularEaseIn**：开始时速度较慢，结束时速度加快的曲线。
- **circularEaseOut**：开始时速度很快，接近终点时速度减慢的圆曲线。
- **circularEaseInOut**：开始时速度较慢，在中间时速度加快，然后在接近终点时速度再次减慢的圆曲线。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve/easeIn
crawled: 2025-12-03T06:14:38Z
---

# easeIn

**Type Property**

A bezier curve that starts out slowly, then speeds up as it finishes.

## Declaration

```swift
static let easeIn: UnitCurve
```

## Discussion

The start and end control points are located at (x: 0.42, y: 0) and (x: 1, y: 1).

## Getting easing curves

- **easeOut**: A bezier curve that starts out quickly, then slows down as it approaches the end.
- **easeInOut**: A bezier curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.
- **circularEaseIn**: A curve that starts out slowly, then speeds up as it finishes.
- **circularEaseOut**: A circular curve that starts out quickly, then slows down as it approaches the end.
- **circularEaseInOut**: A circular curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.

