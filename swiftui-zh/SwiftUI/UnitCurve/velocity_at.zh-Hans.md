---
来源： https://developer.apple.com/documentation/SwiftUI/UnitCurve/velocity(at:)
抓取时间： 2025-12-01T11:03:53Z
---

# velocity(at:)

**实例方法**

返回给定时间内曲线输出值的变化率（一导数）。

## 声明

```swift
func velocity(at progress: Double) -> Double
```

## 参数

- **progress**：输入进度（X 分量）。提供的值被箝位在 [0,1] 范围内。

## 返回值

给定时间内曲线输出值（y 分量）的速度。

## 获取曲线特征

- **value(at:)**：返回给定时间内曲线的输出值（y 分量）。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve/velocity(at:)
crawled: 2025-12-01T11:03:53Z
---

# velocity(at:)

**Instance Method**

Returns the rate of change (first derivative) of the output value of the curve at the given time.

## Declaration

```swift
func velocity(at progress: Double) -> Double
```

## Parameters

- **progress**: The input progress (x component). The provided value is clamped to the range [0,1].

## Return Value

The velocity of the output value (y component) of the curve at the given time.

## Getting curve characteristics

- **value(at:)**: Returns the output value (y component) of the curve at the given time.

