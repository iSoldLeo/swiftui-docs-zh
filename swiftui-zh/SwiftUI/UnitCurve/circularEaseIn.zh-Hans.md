---
来源： https://developer.apple.com/documentation/SwiftUI/UnitCurve/circularEaseIn
抓取时间： 2025-12-03T06:14:40Z
---

# circularEaseIn

**类型属性**

开始时速度较慢，结束时速度加快的曲线。

## 声明

```swift
static let circularEaseIn: UnitCurve
```

## 讨论

曲线的形状等于单位圆的第四象限（右下角）。

## 获取缓和曲线

- **easeIn**：贝塞尔曲线，开始时速度较慢，结束时速度加快。
- **easeOut**：开始时速度很快，接近终点时速度减慢的贝塞尔曲线。
- **easeInOut**：开始时速度较慢，中间时速度加快，接近终点时速度再次减慢的贝塞尔曲线。
- **circularEaseOut**：开始时速度很快，接近终点时速度减慢的圆形曲线。
- **circularEaseInOut**：开始时速度较慢，在中间时速度加快，然后在接近终点时速度再次减慢的圆曲线。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve/circularEaseIn
crawled: 2025-12-03T06:14:40Z
---

# circularEaseIn

**Type Property**

A curve that starts out slowly, then speeds up as it finishes.

## Declaration

```swift
static let circularEaseIn: UnitCurve
```

## Discussion

The shape of the curve is equal to the fourth (bottom right) quadrant of a unit circle.

## Getting easing curves

- **easeIn**: A bezier curve that starts out slowly, then speeds up as it finishes.
- **easeOut**: A bezier curve that starts out quickly, then slows down as it approaches the end.
- **easeInOut**: A bezier curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.
- **circularEaseOut**: A circular curve that starts out quickly, then slows down as it approaches the end.
- **circularEaseInOut**: A circular curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.

