---
来源： https://developer.apple.com/documentation/SwiftUI/UnitCurve/inverse
抓取时间： 2025-12-03T06:14:43Z
---

# 逆

**实例属性**

返回曲线的 x 和 y 分量对调后的副本。

## 声明

```swift
var inverse: UnitCurve { get }
```

## 讨论

逆运算可以反向求解曲线：给定已知的输出（y）值，使用`inverse` 可以求出相应的输入（x）值：

```swift
let curve = UnitCurve.easeInOut

/// The input time for which an easeInOut curve returns 0.6.
let inputTime = curve.inverse.evaluate(at: 0.6)
```


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve/inverse
crawled: 2025-12-03T06:14:43Z
---

# inverse

**Instance Property**

Returns a copy of the curve with its x and y components swapped.

## Declaration

```swift
var inverse: UnitCurve { get }
```

## Discussion

The inverse can be used to solve a curve in reverse: given a known output (y) value, the corresponding input (x) value can be found by using `inverse`:

```swift
let curve = UnitCurve.easeInOut

/// The input time for which an easeInOut curve returns 0.6.
let inputTime = curve.inverse.evaluate(at: 0.6)
```

