---
来源：https://developer.apple.com/documentation/SwiftUI/VectorArithmetic/interpolated(朝:量:)
抓取时间： 2025-12-01T11:04:28Z
---

# interpolated(towards:amount:)

**实例方法**

用`other`对指定的`amount`进行内插，返回该值。

### 声明

```swift
func interpolated(towards other: Self, amount: Double) -> Self
```

## 讨论

这个结果等价于`self + (other - self) * amount`。

## 数值操作

- **magnitudeSquared**：返回此向量算术实例与自身的点积。
- **scale(by:)**：将此值的每个分量与给定值相乘。
- **scaled(by:)**：返回该值的每个分量乘以给定值的值。
- **interpolate(towards:amount:)**：将此值与`other` 插值，并乘以指定的`amount`。


---
source: https://developer.apple.com/documentation/SwiftUI/VectorArithmetic/interpolated(towards:amount:)
crawled: 2025-12-01T11:04:28Z
---

# interpolated(towards:amount:)

**Instance Method**

Returns this value interpolated with `other` by the specified `amount`.

## Declaration

```swift
func interpolated(towards other: Self, amount: Double) -> Self
```

## Discussion

This result is equivalent to `self + (other - self) * amount`.

## Manipulating values

- **magnitudeSquared**: Returns the dot-product of this vector arithmetic instance with itself.
- **scale(by:)**: Multiplies each component of this value by the given value.
- **scaled(by:)**: Returns a value with each component of this value multiplied by the given value.
- **interpolate(towards:amount:)**: Interpolates this value with `other` by the specified `amount`.

