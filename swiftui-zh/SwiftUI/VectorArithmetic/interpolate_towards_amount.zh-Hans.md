---
来源：https://developer.apple.com/documentation/SwiftUI/VectorArithmetic/interpolate(朝:量:)
抓取时间： 2025-12-01T11:04:28Z
---

# interpolate(towards:amount:)

**实例方法**

用指定的`other`对该数值与`other`进行内插。

## 声明

```swift
mutating func interpolate(towards other: Self, amount: Double)
```

## 讨论

这相当于 `self = self + (other - self) * amount`。

## 数值操作

- **magnitudeSquared**：返回此向量算术实例与自身的点积。
- **scale(by:)**：将此值的每个分量与给定值相乘。
- **scaled(by:)**：返回该值的每个分量乘以给定值的值。
- **interpolated(towards:amount:)**：返回该值与`other` 的内插值乘以指定的 `amount`。


---
source: https://developer.apple.com/documentation/SwiftUI/VectorArithmetic/interpolate(towards:amount:)
crawled: 2025-12-01T11:04:28Z
---

# interpolate(towards:amount:)

**Instance Method**

Interpolates this value with `other` by the specified `amount`.

## Declaration

```swift
mutating func interpolate(towards other: Self, amount: Double)
```

## Discussion

This is equivalent to `self = self + (other - self) * amount`.

## Manipulating values

- **magnitudeSquared**: Returns the dot-product of this vector arithmetic instance with itself.
- **scale(by:)**: Multiplies each component of this value by the given value.
- **scaled(by:)**: Returns a value with each component of this value multiplied by the given value.
- **interpolated(towards:amount:)**: Returns this value interpolated with `other` by the specified `amount`.

