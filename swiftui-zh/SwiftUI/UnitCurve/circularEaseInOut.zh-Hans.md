---
来源： https://developer.apple.com/documentation/SwiftUI/UnitCurve/circularEaseInOut
抓取时间： 2025-12-03T06:14:42Z
---

# circularEaseInOut

**类型属性**

一条圆形曲线，开始时速度较慢，中间时速度加快，接近终点时速度再次减慢。

### 声明

```swift
static let circularEaseInOut: UnitCurve
```

## 讨论

曲线的形状由 `circularEaseIn` 和 `circularEaseOut` 的片断组合定义。

## 获取缓和曲线

- **easeIn**：一条贝塞尔曲线，开始时速度较慢，结束时速度加快。
- **easeOut**：开始时速度很快，接近终点时速度减慢的贝塞尔曲线。
- **easeInOut**：开始时速度较慢，中间时速度加快，接近终点时速度再次减慢的贝塞尔曲线。
- **circularEaseIn**：开始时速度较慢，结束时速度加快的曲线。
- **circularEaseOut**：开始时速度很快，接近终点时速度减慢的圆曲线。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve/circularEaseInOut
crawled: 2025-12-03T06:14:42Z
---

# circularEaseInOut

**Type Property**

A circular curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.

## Declaration

```swift
static let circularEaseInOut: UnitCurve
```

## Discussion

The shape of the curve is defined by a piecewise combination of `circularEaseIn` and `circularEaseOut`.

## Getting easing curves

- **easeIn**: A bezier curve that starts out slowly, then speeds up as it finishes.
- **easeOut**: A bezier curve that starts out quickly, then slows down as it approaches the end.
- **easeInOut**: A bezier curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.
- **circularEaseIn**: A curve that starts out slowly, then speeds up as it finishes.
- **circularEaseOut**: A circular curve that starts out quickly, then slows down as it approaches the end.

